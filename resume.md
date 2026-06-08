# 邵正悦 (Zhengyue Shao)

**Senior Android Platform Engineer · Microsoft**
zheshao@microsoft.com

---

## 教育背景

**浙江大学** — 计算机科学与技术 硕士 (2014 – 2017)
- 研究方向：移动安全、移动计算、BYOD 访问控制
- 导师课题组参与移动端用户认证与应用安全管理研究

**南京航空航天大学** — 计算机科学与技术 学士 (2010 – 2014)

---

## 学术发表

1. **RiskCog: Unobtrusive Real-Time User Authentication on Mobile Devices in the Wild**
   T. Zhu, Z. Qu, H. Xu, J. Zhang, **Z. Shao** et al.
   *IEEE Transactions on Mobile Computing*, 2019 | **被引 92 次**

2. **AppShield: Enabling Multi-entity Access Control Cross Platforms for Mobile App Management**
   Z. Qu, G. Guo, **Z. Shao**, V. Rastogi, Y. Chen, H. Chen, W. Hong
   *SecureComm 2016* (Springer LNCS) | **被引 11 次**

---

## 工作经历

### Microsoft — Software Engineer 2 (2017.06 – 至今)

8+ 年 Microsoft 移动端平台工程经验，技术主线从 **Mobile Client Infra** → **Office/Outlook Ecosystem** → **AI-enabled Mobile Platform** → **Copilot Runtime + Realtime AI**，是 Microsoft 365 Copilot Mobile Runtime 的核心基础设施工程师之一。

---

#### 阶段 7：Microsoft 365 Copilot Mobile Runtime — Union / OCM (2025 – 至今)

负责 OneCopilotMobile (OCM) Android SDK 架构与开发，SDK 统一服务于 OfficeMobile、Outlook、Teams 等宿主应用，覆盖数亿用户。角色已从 feature engineer 演进为 **AI Runtime Platform Engineer**。

**AI Context Pipeline & Structured Annotation**
- 设计 AI Context Engineering 层：将用户选中的邮件/文档内容结构化为 Sydney annotation，注入 Copilot reasoning context
- 实现 `SelectedContextMetadata` / Entity Annotation 映射，通过 `postDecorationTransform` 在宿主装饰后注入，解耦 AI 上下文与 UI 层

**Copilot Runtime Infra**
- 负责 BizChat Runtime 核心基础设施：FeatureGator、BizChatConfig、HostConfig、SydneyServiceConfigProvider、CopilotServiceConfigProvider
- 参与 GPT-5 集成、Model Switcher、Query Formulation、Feature Gate rollout 等 AI 能力基础设施
- 负责 Copilot Artifacts / Rich Response / Loop 渲染等下一代 Copilot UX Runtime 方向

**Realtime AI Voice & Reliability**
- 参与 Realtime Chat Voice 链路建设，优化 voice ready latency，处理 realtime session 稳定性
- 修复 voice warmup 在 Private Mode 下的 race condition，重构 reactive flow 管道中的状态原子性
- 作为 BizChat Reliability Incident Owner 之一，处理跨 Outlook/Teams/Union 的生产级 IcM

**合规性迁移 (FluxV4)**
- 为 StreamHub WebSocket 引入合规 HttpClient，确保 SSL Pinning、DLP、审计日志等安全拦截器生效
- 设计双通道路由架构 `RoutingChatServiceFactory`，跨 SDK 与宿主应用两层实现依赖注入链

**Image Upload Consent 系统**
- 设计并实现 MSA 用户图片上传的完整 Notice & Consent 流程，覆盖 Gallery/Camera/Image Edit 三条路径
- 基于 Jetpack Compose 构建声明式 consent 拦截，支持 Feature Gate 灰度、Storage 持久化、异步 Share Intent

**OCM SDK 平台工程**
- 负责 OCM Android SDK 版本发布、Host Config 抽象、跨模块依赖兼容性维护
- ECS rollout 审批与 Feature Flag 生命周期管理（Helix / Taxonomy）

---

#### 阶段 6：Outlook Android — Copilot Integration (2024.06 – 2024.12)

转入 Outlook Mobile 团队，负责 Outlook Android 端 Copilot 集成与搜索体验。

**Outlook Search & Copilot**
- 负责 Outlook 搜索模块：People/Files/Events tab 渲染、空结果 UI、SERP 性能遥测
- 实现 Copilot Page UX、自定义消息渲染框架
- 安全合规：Intune 企业策略检查、SafeLink 集成

---

#### 阶段 5：Teams MeetApp — Meeting Artifact Platform (2022.07 – 2024.05)

转入 **CMD (Calling Meeting Devices) China** 团队，负责 **MeetApp (TFW Meet App)** 的全栈开发（React/TypeScript），为 Teams Desktop 用户提供 AI 增强的会议管理体验。

**会议智能平台 (Meeting Content Platform)**
- 从零构建 MeetApp 核心架构：Graph/Substrate API 客户端、Insight Builder、Calendar 数据管道
- 实现会议 Recap 导航系统：支持从 MeetApp 跳转到会议 Recap 的 AI Notes / @Mentions / Tasks / Recordings 标签页
- 开发 Upcoming / Recent / Missed 会议分类视图，集成 AI Tasks 计数、unfamiliar people insights 等智能功能

**Copilot in MeetApp**
- 设计并实现 MeetApp 内 Copilot 入口，集成 BizChat 对话流（streaming answer、prompt engineering）
- 实现 CrossMeetingCatchUp：利用 GPT-4 生成跨会议摘要
- 对接 Augloop 进行数据分析与 prompt 工程优化

**性能与可靠性**
- 构建实时调试工具（Debug Tool）：支持 UI 日志收集、毫秒级时间戳、日志下载
- 排查内存泄漏（MCP memory breakdown）、导航延迟、on-prem/cloud 用户切换等复杂问题
- 建立性能遥测体系，对接 Kusto 与 Augloop 进行数据驱动优化

**功能迭代与 Rollout**
- 负责多轮 Feature Flag rollout（verifyRecapWithConversationAPI、enableRecentCopilotEntry、enableCallThreadById 等）
- 支持 Channel Meeting、90 天 Recent 扩展、Short URL 处理等产品需求
- 高对比度 / 无障碍适配（Missed pill 样式、键盘导航等）

---

#### 阶段 4：Teams Cortana — Catch Me Up / Play My Messages (2021.01 – 2022.06)

加入 **Skills & Cortana / Distracted Experience** 团队，负责 **Catch Me Up (CMU)** 和 **PMM (Play My Messages)** 的 Teams Android 端开发。332 个 work item，覆盖从 POC 到 GA 全生命周期。

**Catch Me Up — Teams Android 端核心开发**
- 从 POC 到生产：实现 CMU 在 Teams Android 的完整集成，包括 App Module 定义、App Tray 入口、ECS 配置、React Native 桥接
- 开发 React Native 原生模块：CortanaModule（KWS 关键词唤醒）、CatchMeUp Shell（消息操作）、UserStoreModule（缓存）
- 实现消息操作 API：Like / Reply / Mark as Read，桥接到 Teams Mobile SDK messaging API
- 支持 Cortana 语音交互：Hey Cortana 唤醒、AEC（回声消除）、TTS 语音播放、麦克风管理

**PMM (Play My Messages)**
- 实现消息点赞、回复、标记已读等 triage actions 的原生模块
- 开发群聊头像、用户在线状态、振动反馈等 UX 功能

**平台工程**
- Hermes 引擎迁移：将 CMU JS Bundle 迁移到 Hermes 预编译版本
- SDX 迁移：将 CatchMeUp 从旧架构迁移到 SDX，支持 Gov Cloud 部署
- 性能遥测：Android 端 perf metrics、shaker dismiss event、feedback category
- Dev Settings 系统：自定义 flights、Cortana endpoint 切换、Dev/Canary 模式

---

#### 阶段 3：Outlook Mobile — PME / Play My Email (2019 – 2021)

加入 **Outlook Mobile PME (People Mail Events)** 团队，负责 Play My Email 功能的 Android 端开发，为通勤场景提供 AI 驱动的语音邮件播报体验。

**Play My Email — 语音邮件播报**
- 实现 TTS Streaming：在 Outlook Commute 场景中支持语音流式播放邮件内容，优化播放延迟与流畅度
- 开发邮件 triage 操作：语音指令回复、标记、归档，支持 hands-free 邮件处理
- 负责 PME session 稳定性优化（重试机制、网络中断恢复、播放状态管理）

**PME 平台工程**
- 参与 PME 上下文智能层建设：统一 Mail / Calendar / Contacts / Meetings 数据源
- 对接 Cortana 语音引擎，实现邮件内容的自然语言摘要与播报
- 性能遥测与可靠性监控

---

#### 阶段 2：SharePoint Online — SOX Build Infrastructure (2017 – 2019)

加入 **SOX (SharePoint Online Experience) Build vNext** 团队，负责 SharePoint 构建系统现代化。

- **Domino Build Engine 迁移**：将 SharePoint 大型代码库从传统构建系统迁移至 Domino (后更名 BuildXL)，解决 metabuild、OACR 静态分析等兼容性问题
- **构建加速与稳定性**：优化增量构建管道，处理 Pip 依赖哈希、构建缓存失效等生产级构建问题
- **跨分支集成 (Forward Integration)**：负责 devmain → SpoRel 的 FI/merge 与验证，维护分支间构建一致性
- **构建中断处理 (Build Break DRI)**：作为 build break 响应人，执行 backout、重启构建、协调跨团队修复

---

## 技术技能

- **语言：** Kotlin, Java, TypeScript, React, Python, Rust
- **Android：** Jetpack Compose, Kotlin Coroutines/Flow, Dagger/Hilt, OkHttp/WebSocket, Room, React Native
- **Web/Desktop：** React, TypeScript, Teams SDK, React Native Bridge, Hermes Engine
- **AI Runtime：** GPT Integration, AI Context Pipeline, Prompt Engineering, Model Switching, Feature Gating, Augloop
- **架构：** MVVM, Clean Architecture, SDK 设计, 响应式编程, 依赖注入, Host/Plugin 架构
- **Realtime：** WebSocket, Streaming, Voice Session (TTS/AEC/KWS), Transcription Pipeline
- **构建系统：** Domino/BuildXL, OACR, Forward Integration, Monorepo CI/CD
- **安全合规：** SSL Pinning, DLP, Intune MDM, 审计日志, SafeLink
- **平台工程：** ECS Rollout, Feature Flag Infra, Telemetry/Kusto, Incident Management
- **工具：** Azure DevOps, Git Monorepo, Gradle, ADB, Graph API, Substrate API

