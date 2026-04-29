# SVG简易编辑器 SDK 技术方案

## 1. 背景与定位
本项目旨在提供一个轻量级、开箱即用的 SVG 简易编辑器 SDK。基于底层的 `@baidu/orion-svg-sample-editor` (PosterEditor) 进行二次封装，补齐完备的 UI 交互与工程化能力。通过统一的接口设计，为上层业务提供一致的文本编辑、富文本属性调节（字号、颜色）、历史记录以及多格式导出能力。

## 2. 整体架构设计

项目采用**严格的分层解耦设计**，确保 SDK 的高可维护性与易扩展性，且完全兼容不同的前端框架环境。

![SVG简易编辑器整体架构图](../image/svg-web-editor-architecture.png)

1. **状态逻辑层 (`useEditorState`)：** 作为唯一持有底层实例（`PosterEditor`）的入口，负责监听引擎内部事件，并向外暴露全局响应式状态（如当前选中节点、编辑状态、字号、颜色、撤销重做栈大小等）。
2. **统一服务层 (`EditorCommandService`)：** 对底层 API 做了面向业务的二次封装与抽象。将扁平的方法分类到不同命名空间下（如 `text`、`font`、`history`、`export`），屏蔽底层引擎变更对 UI 层的直接影响。
3. **视图展示层 (UI Components)：** 纯纯粹的展示与交互组件，**绝不直接操作或持有底层引擎实例**。UI 层只接收状态层的 Props，用户交互时调用服务层的命令，随后引擎触发事件重新流转至状态层更新视图。
4. **多版本适配层：** 采用 Monorepo 架构（`pnpm workspace`），核心逻辑代码收敛在 `packages/core`，通过重导出机制，在 `packages/vue2` 与 `packages/vue3` 中根据宿主环境打包出对应依赖的发布产物。

## 3. 核心 API 与接口定义

### 3.1 `SvgEditor.vue` 对外组件接口

**Props (组件参数):**

| 属性名 | 类型 | 默认值 | 描述 |
| --- | --- | --- | --- |
| `svgHtml` | `String` | `''` | 初始化的 SVG 字符串内容。组件挂载后，底层引擎会解析并渲染此字符串。 |
| `editStatus` | `String` | `'editing'` | 编辑器当前状态枚举。支持 `'editing'` (编辑模式) 和 `'preview'` (预览模式：会隐藏所有工具栏)。 |

**Slots (插槽扩展):**

| 插槽名 | 描述 |
| --- | --- |
| `left` | 位于顶部操作栏(`EditorTopBar`)左侧的预留区域，业务方可在此注入自定义内容（如标题、返回按钮等）。 |
| `download` | 位于顶部操作栏最右侧。提供该插槽时，将**完全覆盖 SDK 默认的“下载”下拉组件**，交由业务方自行实现导出逻辑。 |

### 3.2 `EditorCommandService` 服务层接口

SDK 将对底层的操作按命名空间隔离：

*   **`commands.text` (文本处理):**
    *   `add(str: string)`: 插入新的文本节点。
    *   `setContent(node: any, str: string)`: 修改指定节点的文本内容，支持换行。
    *   `enterEdit(node: any)`: 触发指定文本节点进入行内输入编辑状态。
    *   `exitEdit()`: 强制退出当前的行内输入状态。
*   **`commands.font` (字号字色):**
    *   `setSize(node: any, size: number)` / `getSize(node)`: 设置与读取文本字号。
    *   `setColor(node: any, color: string)` / `getColor(node)`: 设置与读取文本颜色（HEX/RGB/HSV）。
*   **`commands.history` (历史记录):**
    *   `undo()` / `redo()`: 执行撤销 / 重做。
    *   `getUndoSize()` / `getRedoSize()`: 获取当前撤销重做栈大小，用于 UI 按钮禁用状态控制。
*   **`commands.export` (文件导出):**
    *   `getSvg()`: 获取标准 XML 格式的 SVG 字符串文本（内部补齐了 `xmlns` 等外壳，可直接保存为 `.svg` 文件）。
    *   `toPng(config)`: 基于 `PosterExportService`，将当前画板转换为 PNG Base64 数据，支持异步等待。

## 4. 核心交互流程与实现细节

### 4.1 上下文工具栏精准跟随 (Context Toolbar Positioning)
`EditorContextToolbar`（上下文浮层）通过结合 `ResizeObserver` (监听画布与元素尺寸变化) 和 `MutationObserver` (监听 DOM 结构与 transform 矩阵变化)，实现了对 SVG 选中元素的高性能实时跟踪。
*   **碰撞检测机制：** 默认优先在元素正上方居中显示。当元素极度靠近顶部边界时，自动翻转至元素下方；当元素靠近左右边界时，自动执行横向夹紧处理以防止工具栏溢出视口。

### 4.2 导出逻辑与防重入
导出涉及浏览器环境的 Blob 及 Base64 转换：
*   点击导出时，按钮强制处于 Loading 状态拦截重复点击（防重入）。
*   利用原生的 `a.download` 属性与 `URL.createObjectURL(blob)` 实现前端纯本地下载，下载结束自动清理内存。

## 5. 待支持能力与底层依赖清单 (TODOs)

SDK 代码中已通过 `[NEEDS-NATIVE-API]` 标识对缺少底层能力的功能进行了拦截或 UI 占位处理，主要包括：

1.  **基础富文本样式控制**：文本的 B（加粗）、I（斜体）、U（下划线）、S（删除线）。UI 层预置了对应按钮但保持 Disabled，需等待底层提供诸如 `changeFontWeight` 等读写 API。
2.  **画布视图控制**：画布放大 / 缩小 / 旋转等 API，目前 Service 侧作为占位函数。
3.  **其他导出格式**：默认 ExportDropdown 预留了导出 PPTX 的入口，暂无实现。
