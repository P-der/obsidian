---
title: AI 垂类业务场景与应用深度解析
updated: 2026-04-24
tags: [AI, 垂类应用, 综述]
---

# AI 垂类业务场景与应用深度解析

> 本文档于 2026-04-24 做全量修订：核验所有外链、修正过时信息、统一格式。
> 仍存疑的数据已标注 `⚠️ 未核实 / 口径存疑`。

## 目录

- [一、图像 AI](#一图像-ai)
- [二、视频 AI](#二视频-ai)
- [三、音频 AI](#三音频-ai)
- [四、文本 AI](#四文本-ai)
- [五、代码 AI](#五代码-ai)
- [六、跨垂类融合](#六跨垂类融合)
- [七、总结](#七总结)
- [附录：官方链接汇总](#附录官方链接汇总)

---

## 一、图像 AI

### 1.1 电商产品图生成

**场景**：电商卖家需批量产出主图、场景图、详情页素材。AI 可从白底图自动生成场景图、去背景、扩图、生成套图。

#### 国际方案

| 应用 | 核心特色 | 成本 | 适用场景 |
| --- | --- | --- | --- |
| **Stable Diffusion + ControlNet** | 开源可本地部署；ControlNet 精确控制姿态/深度/边缘；社区 LoRA 生态 | 免费（需 GPU） | 数据敏感的企业内部；批量自动化 |
| **GPT Image 1.5（OpenAI）** | LM Arena 2026-03 排名第一（ELO 1264）；文字渲染能力最强；与 ChatGPT 深度集成 | API 约 $0.04–0.08/张；ChatGPT Plus $20/月 | 营销物料、带文字的产品图 |

> **更新说明**：DALL-E 3 将于 2026-05-12 关停 API，由 `gpt-image-1` / `gpt-image-1.5` 全面接替；ChatGPT 内图像生成已默认使用 GPT Image。

#### 国内方案

| 应用 | 核心特色 | 成本 | 适用场景 |
| --- | --- | --- | --- |
| **通义万相**（阿里） | 电商场景深度优化；服装平铺图 → 模特上身；批量 SKU | 按量计费 | 淘宝/天猫/1688 生态 |
| **文心一格**（百度） | 已整合进入文心一言；中文提示词理解佳；国风元素 | 免费 + 付费 | 国内品牌、中文内容 |
| **爱创 AI**（https://www.51aic.com/） | 1688 星工具服务商；一键全店素材；模特试穿/换色 | 低门槛 | 1688 商家、中小卖家 |

> **口径提示**：文中原稿引用的 "点击率 +171%"、"单款节省 800 元" 等均来自厂商案例宣传，非独立第三方数据。

#### 横向对比

| 应用 | 优势 | 劣势 | 目标人群 |
| --- | --- | --- | --- |
| Stable Diffusion | 开源、高可控 | 技术门槛、算力需求 | 技术团队 |
| GPT Image 1.5 | 文字渲染+提示词还原 | 需境外网络 | 跨境电商、高端设计 |
| 通义万相 | 阿里生态 | 局限阿里系 | 淘宝天猫商家 |
| 文心一格 | 中文/国风/合规 | 艺术性一般 | 国内品牌 |
| 爱创 AI | 一键全套素材 | 风格较固定 | 1688 商家 |

---

### 1.2 艺术创作与概念设计

| 应用 | 核心特色 | 成本 |
| --- | --- | --- |
| **Midjourney V7 / V8-Alpha** | 艺术表现力标杆；V7 为 2025-06 起默认模型，V8-Alpha 于 2026-03 进入预览 | Basic $10/月起 |
| **GPT Image 1.5**（OpenAI） | 文字渲染、透视、光照极佳；LM Arena ELO 1264 | API 约 $0.04–0.08/张 |
| **Stable Diffusion / Flux** | 开源生态、社区 LoRA 丰富 | 免费 |

> **说明**：原稿"Midjourney V6"已过时，当前主版本为 V7；V8-Alpha 处于预览阶段。

---

### 1.3 AI 动漫 / 二次元

| 应用 | 核心特色 | 成本 |
| --- | --- | --- |
| **NovelAI**（https://novelai.net/） | 二次元风格纯正；支持 Danbooru 标签 | Tablet $10 / Scroll $15 / **Opus $25** |
| **Midjourney Niji** | 官方动漫模式；高分辨率原生 | $10–60/月 |
| **触站 AI**（https://www.czhanai.com/） | 国内最大二次元 AI 社区；中文提示词 | 免费 + 会员 ¥19–49/月 |
| **画宇宙**（https://creator.nolibox.com/） | 一站式创作平台；多风格模型 | 免费 + 会员 ¥29–99/月 |
| **吐司 AI**（https://tusi.cn/） | 国内直连；丰富 LoRA 社区模型 | 免费 + 会员 ¥24.9–39.9/多种周期 |
| **Animagine XL 3.1** | 开源动漫专精 SDXL 模型；Cagliostro Lab | 免费 |

#### 国内外对比

| 维度 | 国际（NovelAI / Niji） | 国内（触站 / 画宇宙 / 吐司） |
| --- | --- | --- |
| 画风纯度 | 日系动漫感极强 | 略弱，但差距缩小 |
| 提示词 | 英文 + Danbooru | 中文友好 |
| 成本 | $10–25/月 | 免费额度 + ¥19/月起 |
| 访问 | 需境外网络 | 国内直连 |
| 社区 | 全球资源最丰富 | 本土内容丰富 |

---

### 1.4 生成式视觉浏览器（实验性新形态）

> 一个把"浏览网页"变成"翻看一本无限生成的图画书"的新场景，代表了图像 AI 从"产素材"走向"造界面"的方向。

**Flipbook**（https://flipbook.page/）

- **一句话说明**：一个完全由图像模型实时生成的"无限视觉浏览器"——每一"页"都是一张 AI 生成的图片，点击图中任意元素就会生成一张对它展开探索的新图，整个浏览过程没有 HTML、没有代码、没有真实链接。
- **作者**：Zain Shah、Eddie Jiao、Drew Carr（实验项目）
- **核心特色**：
  - 所有内容（含文字）均由图像模型渲染
  - "点击图像中的物体"=下一次生成的 prompt
  - 可选 **Live Video Stream**：把静态页之间的跳转转为连续动画流（高耗资源，可开关）
- **场景价值**：
  - 开放式学习/探索：像翻百科全书一样任意深挖
  - 对"生成式 UI"方向的概念验证——把"大段文字 + 色块"的传统界面，换成图像原生交互
  - 为图像/视频模型性能提升后的"图像即应用"形态提供原型
- **局限**：
  - 目前定位为"实验"，无真实数据与状态持久化
  - 资源消耗高，交互可预测性有限
- **延伸思考**：当图像/视频模型推理成本与精度进一步改进，"在 Flipbook 里直接订机票、办事"并非不可能——这正是作者设想的"生成式 OS/浏览器"方向。

---

## 二、视频 AI

### 2.1 电商带货短视频

#### 国际方案

| 应用 | 核心特色 | 备注 |
| --- | --- | --- |
| **Runway Gen-4.5 / GWM-1** | Motion Brush 区域控制；原生 1080p，支持导出 4K（8K 为 AI 升采样） | 原稿"Gen-4 / 8K 原生"不准确 |
| **Luma Ray3 / UNI-1** | 2026-01 发布 Ray3；生成极速；统一多模态模型 UNI-1 | 原稿"Dream Machine 2.0"已过时 |
| **OpenAI Sora 2** | 当前最长 **25 秒（Pro 订阅）**，1080p；支持音画同生 / Character Cameo | 原稿"Sora Pro 2026 / 4K / 分钟级"不准确 |

#### 国内方案

| 应用 | 核心特色 | 备注 |
| --- | --- | --- |
| **快手可灵 3.0**（https://klingai.kuaishou.com/） | 2026-02-05 发布；最长 **15 秒**；智能分镜；4K 原生 | 原稿"30 秒"应更正为 15 秒 |
| **字节 Seedance 2.0**（即梦） | 2026-02 发布；4–15 秒；抖音生态直出 | 原稿"12 秒"应更正为 15 秒 |
| **沃创 Wocreate**（https://wocreate.ai/） | URL 商品解析 → 带货视频；电商 Agent 模板 | 验证 ✅ |
| **阿里 HappyHorse-1.0** | 2026-04-09 开源；**15B 参数**（非 150B）；音画联合生成；Artificial Analysis Video Arena ELO 1333–1413 | 原稿参数量错误 10 倍；许可证官方未明示 Apache 2.0；`happyhorseprompt.com` **非官方** |
| **Vidu**（https://www.vidu.cn/） | 多主体一致性；参考生视频 | ✅ |
| **Pika**（https://pika.art/） | Pikaformance 模型；高保真表情；音频同步 | ✅ |

> **数据勘误**：原稿 "AI 漫剧 2025 市场 189.8 亿 / +276.3%" 与 DataEye 研究院口径不符，后者给出的数字为 **2025 年约 168 亿**、2026 年预计 240 亿（同比 +40% 左右）。

---

### 2.2 数字人与虚拟主播

- **HeyGen**（https://www.heygen.com/）：**175+ 语言与方言**（原稿"100+"偏低）；LiveAvatar 强调低延迟（官方未披露具体毫秒数）。
- **国内数字人**：24 小时直播、批量讲解、深夜高转化场景。
- **市场规模**（来源：艾媒咨询白皮书）：**2025 年核心市场 480.6 亿元**（非 2026 年），带动产业规模约 6402.7 亿元。

---

### 2.3 AI 漫剧 / 仿真人短剧

#### 市场数据（含勘误）

- **2025 年市场规模**：约 **168 亿元**（DataEye），2026 年预计 **240 亿**。`⚠️ 原稿"189.8 亿 / +276.3%"未在主流研报中出现`。
- **爆款案例**：《斩仙台下，我震惊了诸神！》抖音播放 **11.5 亿**（✅ 已核实）。
- `⚠️ 原稿《霍去病》"3 人 48 小时 3000 元 80 集 播放 5 亿"已被导演杨涵涵公开辟谣`：
  - 实际仅两段 4–6 分钟短片，非 80 集；
  - 团队近 20 人，非 3 人；
  - 3000 元仅算力成本；48 小时为纯工时；
  - 5 亿播放量导演本人无法核实；
  - 制作方为 360 集团"纳米漫剧流水线"。
- `⚠️ 原稿"郑州日新月异裁员 400–500 人"无公开来源支撑`，建议删除或标注存疑。

#### 主流制作工具

- **Seedance 2.0 / 即梦**（https://jimeng.jianying.com/）：抖音生态；写实风格。
- **万彩动画大师**（https://www.animiz.cn/）：MG 动画+照片数字人；**非** AI 视频生成模型。
- **可灵 + 角色一致性 LoRA**：仿真人短剧主力。
- **ComfyUI**（https://www.comfy.org/zh-cn/）：本地节点式工作流；可控性最强。

---

## 三、音频 AI

### 3.1 有声书与播客

#### 国际方案

| 应用 | 核心特色 | 成本 |
| --- | --- | --- |
| **ElevenLabs**（https://elevenlabs.io/） | Eleven v3 支持 **70+ 语言**（非 30+）；高拟真；情感与呼吸自然 | 订阅制 |
| **Play.ht**（https://play.ht/） | 品牌语音定制；SSML；800+ 音色，140+ 语言 | 商业订阅 |
| **Fish Audio**（https://fish.audio/） | 情感表现力强；免费额度 **8000 credits / 月（约 7 分钟，500 字符/次）** | 免费+订阅 |

> **勘误**：原稿 Fish Audio"8000 字符免费" → 应为 **8000 credits / 月**，每次最多 500 字符。

#### 国内方案

| 应用 | 核心特色 | 成本 |
| --- | --- | --- |
| **冬瓜配音**（https://www.okaidub.com/） | 多角色模式；方言丰富；厂商宣称 99.8% 还原 / 700+ 音色（⚠️ 官网并未公开该数字，来自第三方测评） | 会员制 |
| **百宝音** | 微信小程序/APP/网页三端；长文本朗读、多音字修正 | 免费+会员 |
| **MiniMax Speech 2.6**（https://www.minimaxi.com/） | 低延迟、高情感表现 | 付费 |
| **ChatTTS**（https://github.com/2noise/ChatTTS） | 代码 **AGPLv3**；**模型 CC BY-NC 4.0**，仅限非商用 | 免费（非商用） |

> **勘误**：原稿"ChatTTS 永久免费 / 终身免费"需限定为**非商业用途**；商业化需联系授权。

---

### 3.2 AI 播客听书模式

**书尖 AI**：基于阿里云 AI 的听书/阅读 App，1.2 亿册书库；双主持人 AI 播客模式。
> `⚠️ 原稿"完听率 85% / 周均 42 小时"未在公开资料中核实到，建议删除或标注为厂商口径。`

---

## 四、文本 AI

### 4.1 企业知识库与 RAG

**RAG 流程**：索引 → 检索 → 生成。

**2026 年演进方向**：
- 自适应检索（按问题复杂度决策）
- 图检索（Graph RAG）支持多跳推理
- 全局摘要引导的检索
- 流式实时 RAG

#### 向量数据库

| 库 | 规模 | 部署 | 成本 |
| --- | --- | --- | --- |
| FAISS（https://github.com/facebookresearch/faiss） | 中小（百万级） | 本地 | 免费 |
| Milvus（https://milvus.io/） | 大（千万级+） | 本地/云 | 免费 / 企业版 |
| Pinecone（https://www.pinecone.io/） | 中 | 云 SaaS | 订阅制 |
| Qdrant（https://qdrant.tech/） | 中大 | 本地/云 | 免费 / 云付费 |

---

### 4.2 LLM Agent（智能体）

#### 对比

| 能力 | 传统对话 AI | LLM Agent |
| --- | --- | --- |
| 交互 | 单轮问答 | 多轮任务导向 |
| 工具 | 不支持 | 支持 API/数据库/系统命令 |
| 记忆 | 单会话 | 跨会话 |
| 自主性 | 被动响应 | 主动规划+反思修正 |

#### 平台

- **国际**：
  - **OpenAI Responses API**（https://platform.openai.com/docs/api-reference/responses）—— 2026 当前推荐栈
  - ⚠️ 原 **Assistants API** 已于 2025-08-26 宣布弃用，2026-08-26 关停
  - **LangChain**（https://www.langchain.com/）
  - **AutoGPT**（https://github.com/Significant-Gravitas/AutoGPT）
- **国内**：
  - 百度 **文心智能体平台**（https://agents.baidu.com/）
  - **通义千问 Agent**（https://tongyi.aliyun.com/）
  - **腾讯元宝**（https://yuanbao.tencent.com/）
  - **豆包**（https://www.doubao.com/）
  - **文心一言 / 文小言**（https://yiyan.baidu.com/）—— 消费端已更名"文小言"

---

### 4.3 周报助手（百度 WorkOS）

- 数据融合：知识库 + iCode + iCafe + 会议记录
- 历史周报风险/行动建议
- OKR 结构化填充
- 自动保存到个人知识库并附链接

---

## 五、代码 AI

### 5.1 智能代码生成与补全

#### 国际

| 应用 | 官方 URL | 备注 |
| --- | --- | --- |
| **GitHub Copilot** | https://github.com/features/copilot | 官方研究：小任务 **55.8% 提速**（95% CI 21–89%，p=0.0017）。`⚠️ 原稿"85% confidence"为对置信区间的误读` |
| **Cursor** | https://cursor.com/（原 cursor.sh 已跳转） | 项目级上下文；Tab 预测（新版名为 "Fusion"） |
| **Windsurf**（Cognition, Inc.） | https://windsurf.com/ | 原 Codeium 品牌；2025-07 Google 关键团队 acquihire，随后 Cognition 收购剩余业务 |
| **Trae**（字节跳动） | https://www.trae.ai/ | 基于 VSCode 的独立 AI IDE；mac/Win |
| **Qodo**（原 CodiumAI） | https://www.qodo.ai/ | 2024-09 重命名 |
| **Replit** | https://replit.com/ | 在线 IDE + Agent |

#### 国内

| 应用 | 官方 URL | 备注 |
| --- | --- | --- |
| **文心快码 Comate** | https://comate.baidu.com/ | IDC 评测 C++ 代码生成第一；百度内部研发提效 60%；喜马拉雅 AI 代码占比 ~33% |
| **通义灵码** | https://tongyi.aliyun.com/lingma | 基于通义千问；200+ 语言 |
| **腾讯云 CodeBuddy** | https://copilot.tencent.com/ | `⚠️ 原链接 /product/tca 非代码助手` |

---

### 5.2 AI 代码审查

| 工具 | 官方 URL |
| --- | --- |
| **SonarQube** | https://www.sonarsource.com/products/sonarqube/ |
| **DeepSource** | https://deepsource.com/ |
| **Snyk Code** | https://snyk.io/product/snyk-code/ |
| **百度 iCode 智能 CR** | 内部平台 |

---

### 5.3 自动化测试

| 工具 | 官方 URL | 特色 |
| --- | --- | --- |
| **TestRigor** | https://testrigor.com/ | 纯自然语言测试；自愈 |
| **Applitools** | https://applitools.com/ | 视觉回归 |
| **Parasoft** | https://www.parasoft.com/ | C/C++ AI 用例生成；MC/DC 覆盖 |

---

### 5.4 DevOps 全流程

- 需求（iCafe/Jira）→ 代码（Comate）→ 提交 → AI CR → 流水线 → 监控
- 百度实测：研发效能 +60%、部署频率 5×、MTTR -80%（内部数据，口径见原文）

---

## 六、跨垂类融合

### 6.1 多模态内容创作

- **豆包**（字节）：文+图+视频+音频一体化；抖音/今日头条整合。

### 6.2 数字孪生 / 虚拟世界

- 组合：图像（纹理）+ 视频（动画）+ 音频（NPC 语音）+ 文本（剧情）+ 代码（逻辑）。
- 场景：游戏、虚拟展厅、工业数字孪生。

### 6.3 AI 数字人直播（视频+音频+文本）

- **HeyGen**（国际）：175+ 语言；实时交互。
- **小冰数字人**（https://www.xiaoice.com/）、**立得客登登** 等本地化部署方案 `⚠️ 后者仅在 SEO 类稿件出现，影响力有限`。
- **市场规模**：艾媒咨询白皮书 2025 年核心市场 **480.6 亿元**。

### 6.4 具身智能 / 人形机器人

> 2026 年被业界视为"具身智能商用元年"。

#### 技术栈

| 层 | 对应垂类 | 能力 |
| --- | --- | --- |
| 感知大脑 | 视频 + 音频 AI | 视觉识别、深度感知、声源定位 |
| 决策大脑 | 文本 AI（LLM Agent） | 任务规划、推理 |
| 世界模型 | 多模态 | 物理规律、因果推理 |
| 运动小脑 | 代码 AI | 运动控制、力反馈 |
| 硬件执行 | 机电 | 精密抓取、双足 |

#### 代表企业

**中国**
- **智元（AGIBOT）**（https://www.agibot.com.cn/ | EN: https://www.agibot.com/ | 备用：https://www.zhiyuan-robot.com/）
  - 产品线：**远征 / 灵犀 / 精灵 / 酷拓（四足）/ 绝尘（清洁）/ OmniHand**（`⚠️ 原稿"探索系列"不存在`）
  - 营收（APC 2026 官方披露）：2023 ~30 万 → 2024 ~6000 万 → **2025 10.5 亿**；**2027 目标破 100 亿**（原稿 2026 破百亿错误）
  - **AIMA（AI Machine Architecture）** 2026-04-17 APC 首发
- **优必选**（https://www.ubtrobot.com/）
- **未来不远 Futuring Robot**：家庭服务机器人；2026-01 完成 2 亿元天使轮；端到端 AVLA 模型

**国际**
- **Figure AI**（https://www.figure.ai/）：`⚠️ 2025-02-04 已终止与 OpenAI 合作，改用自研 Helix（VLA）模型`；Figure 02 已部署 BMW Spartanburg 工厂（原稿"GPT-6 驱动"不准确）
- **Tesla Optimus**（https://www.tesla.com/optimus）：Gen 3 低量产 2026 夏（Fremont），高量产 2027 夏（Giga Texas，规划年产 1000 万台）

---

## 七、总结

| 垂类 | 代表应用（国际） | 代表应用（国内） | 2026 趋势 |
| --- | --- | --- | --- |
| 图像 | Midjourney V7 / GPT Image 1.5 / SD / NovelAI | 通义万相 / 文心一格 / 爱创 AI / 触站 AI | 场景垂直化、动漫风格、可控性增强 |
| 视频 | Runway Gen-4.5 / Sora 2 / Ray3 | 可灵 3.0 / Seedance 2.0 / 沃创 / HappyHorse-1.0 | AI 漫剧爆发、智能分镜、音画同生 |
| 音频 | ElevenLabs v3 / Play.ht / Fish Audio | 冬瓜配音 / MiniMax Speech 2.6 / ChatTTS | 情感化、多语言、实时交互 |
| 文本 | ChatGPT / Claude / Gemini | 通义千问 / 豆包 / 文心（文小言） | Agent 商用元年；Responses API 成主流 |
| 代码 | Copilot / Cursor / Windsurf / Trae | 文心快码 / 通义灵码 / 腾讯云 CodeBuddy | 全流程 DevOps、规范驱动 |
| 融合 | HeyGen / Figure / Tesla Optimus | 小冰 / 智元 / 优必选 / 未来不远 | 数字人 7×24 直播、人形机器人商用 |

---

## 附录：官方链接汇总

### 图像 AI
- Stable Diffusion: https://stability.ai/
- ControlNet: https://github.com/lllyasviel/ControlNet
- DALL-E 3（2026-05-12 API 关停）: https://openai.com/index/dall-e-3/
- GPT Image 1.5: https://openai.com/
- Midjourney: https://www.midjourney.com/
- 通义万相: https://tongyi.aliyun.com/wanxiang
- 文心一格（已并入文心一言）: https://yige.baidu.com/
- 爱创 AI: https://www.51aic.com/
- NovelAI: https://novelai.net/
- 触站 AI: https://www.czhanai.com/
- 画宇宙: https://creator.nolibox.com/
- 吐司 AI: https://tusi.cn/
- Animagine XL 3.1: https://huggingface.co/cagliostrolab/animagine-xl-3.1
- Flipbook（生成式视觉浏览器 / 实验项目）: https://flipbook.page/

### 视频 AI
- Runway: https://runwayml.com/
- Luma Labs: https://lumalabs.ai/
- OpenAI Sora: https://openai.com/sora
- HeyGen: https://www.heygen.com/
- 快手可灵: https://klingai.kuaishou.com/
- 字节即梦 Seedance: https://jimeng.jianying.com/
- 沃创 Wocreate: https://wocreate.ai/
- 阿里 HappyHorse-1.0: 官方渠道以阿里官宣为准（`⚠️ happyhorseprompt.com 非官方`）
- Vidu: https://www.vidu.cn/
- Pika: https://pika.art/
- 万彩动画大师: https://www.animiz.cn/
- ComfyUI: https://www.comfy.org/zh-cn/

### 音频 AI
- ElevenLabs: https://elevenlabs.io/
- Play.ht: https://play.ht/
- Fish Audio: https://fish.audio/
- 冬瓜配音: https://www.okaidub.com/
- ChatTTS: https://github.com/2noise/ChatTTS
- MiniMax: https://www.minimaxi.com/
- 剪映 / CapCut: https://www.capcut.com/
- 腾讯智影: https://zenvideo.qq.com/

### 文本 AI
- ChatGPT: https://chatgpt.com/
- Claude: https://claude.ai/
- Gemini: https://gemini.google.com/
- OpenAI Responses API: https://platform.openai.com/docs/api-reference/responses
- LangChain: https://www.langchain.com/
- AutoGPT: https://github.com/Significant-Gravitas/AutoGPT
- 通义千问: https://tongyi.aliyun.com/
- 豆包: https://www.doubao.com/
- 文心一言 / 文小言: https://yiyan.baidu.com/
- 腾讯元宝: https://yuanbao.tencent.com/
- 百度文心智能体平台: https://agents.baidu.com/

### 向量数据库
- FAISS: https://github.com/facebookresearch/faiss
- Milvus: https://milvus.io/
- Pinecone: https://www.pinecone.io/
- Qdrant: https://qdrant.tech/

### 代码 AI
- GitHub Copilot: https://github.com/features/copilot
- Cursor: https://cursor.com/
- Windsurf: https://windsurf.com/
- Trae: https://www.trae.ai/
- Qodo（原 CodiumAI）: https://www.qodo.ai/
- Replit: https://replit.com/
- 文心快码 Comate: https://comate.baidu.com/
- 通义灵码: https://tongyi.aliyun.com/lingma
- 腾讯云 CodeBuddy: https://copilot.tencent.com/

### 代码审查
- SonarQube: https://www.sonarsource.com/products/sonarqube/
- DeepSource: https://deepsource.com/
- Snyk Code: https://snyk.io/product/snyk-code/

### 自动化测试
- TestRigor: https://testrigor.com/
- Applitools: https://applitools.com/
- Parasoft: https://www.parasoft.com/

### 具身智能 / 数字人
- 智元 AGIBOT: https://www.agibot.com.cn/ ・ https://www.agibot.com/
- 优必选: https://www.ubtrobot.com/
- Figure AI: https://www.figure.ai/
- Tesla Optimus: https://www.tesla.com/optimus
- 小冰数字人: https://www.xiaoice.com/

---

## 本次修订主要变更（2026-04-24）

1. **版本/型号更正**：Midjourney V6→V7/V8-Alpha；Runway Gen-4→Gen-4.5；Luma Dream Machine 2.0→Ray3；Sora Pro→Sora 2（25s/1080p）；可灵 30s→15s；Seedance 12s→15s；HappyHorse 150B→15B。
2. **链接更新**：Cursor cursor.sh→cursor.com；Windsurf codeium.com→windsurf.com；CodiumAI→Qodo；腾讯云 TCA→CodeBuddy；ChatGPT 主域名→chatgpt.com。
3. **API 弃用**：OpenAI Assistants API 将于 2026-08-26 关停，改用 Responses API。
4. **事实辟谣**：《霍去病》数据已被导演辟谣；"郑州日新月异裁员"无公开来源。
5. **数据口径**：AI 漫剧 2025 市场 168 亿（非 189.8 亿）；数字人 480.6 亿为 2025 年核心市场；ElevenLabs 70+ 语言；HeyGen 175+ 语言；Fish Audio "8000" 单位为 credits 非字符。
6. **产品归属**：Figure AI 与 OpenAI 已于 2025-02 终止合作，采用自研 Helix 模型；智元产品线无"探索系列"，2027（非 2026）目标百亿。
7. **许可限定**：ChatTTS 模型权重为 CC BY-NC 4.0，禁止商用。
