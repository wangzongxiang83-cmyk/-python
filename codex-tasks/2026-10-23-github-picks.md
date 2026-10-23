# 给 Codex 的任务包：GitHub 热榜收藏项目试跑评估

> 来源：Muse（Carter 的个人助理）2026-10-23 整理自 GitHub 每日热榜。
> 读者：运行在 Carter 电脑上的 Codex。本文件自包含，不需要额外上下文。
> 总原则：先评估、后安装；重型安装（大模型/大依赖）动手前先在结果文件里写清方案，等 Carter 在会话里确认再执行。

## 背景（一句话版）

Carter 在做三件事，评估时按这个尺子打分：①抖音口播/数字人短视频获客；②AI 建站接单（落地页/多页站/AI 组件）；③微信客服知识库（本地 qwen3:14b + 法规长文档，运行在 5070Ti 机器上）。成本敏感：优先免费/本地/开源，付费 API 默认不用。

## 项目清单（已由 Muse 核过仓库元数据：星数/许可证/描述）

### 1. debpalash/VoiceStudio — 优先级最高（自用工具方向）
- 描述：开源、全本地的 ElevenLabs 替代品：声音克隆、声音设计、视频配音、听写、转录、有声书，号称 646 种语言。
- 许可证：**AGPL-3.0** —— 只可自用；不得作为给客户的产品/服务底座（AGPL 网络服务源码公开义务）。
- 用途设想：抖音口播/数字人配音环节本地化，替代付费 TTS。

### 2. heygen-com/hyperframes — 优先级高（可商用方向）
- 描述：Write HTML. Render video. Built for agents.
- 许可证：**Apache-2.0** —— 商用友好。
- 用途设想：用 HTML 生成短视频：建站 gig 演示视频、客户广告视频样片。

### 3. VectifyAI/PageIndex — 优先级中（知识库对比实验）
- 描述：Document Index for Vectorless, Reasoning-based RAG（不用向量库、靠推理做长文档索引）。
- 许可证：MIT。
- 用途设想：和现有向量方案对比，在长文档（法规类）上的检索准确率。**只能用公开/样例文档测试，禁止使用任何真实客户资料。**

### 4. Panniantong/Agent-Reach — 优先级中（先查风险，不登录主账号）
- 描述：一个 CLI 让 Agent 读取/搜索 Twitter、Reddit、YouTube、GitHub、Bilibili、小红书，号称零 API 费。
- 许可证：MIT。
- 风险提示：本质是平台抓取。先只做只读调查（安装方式、登录方式、封号风险点），**不要登录 Carter 的任何主账号**；真要试用小号并经 Carter 确认。

### 5. 只收藏、暂不试跑
- stablyai/orca（MIT）：多 coding agent 舰队管理（桌面/手机/远程）。
- HKUDS/CLI-Anything（Apache-2.0）：把软件变成 Agent 可调用的 CLI。
- anomalyco/opencode（MIT）：开源 coding agent，Codex 的备胎选项。
- thedotmack/claude-mem（Apache-2.0）：跨会话持久记忆，兼容 Codex 等多个 agent。

### 6. 明确不要安装/不要运行（Muse 已判定）
- morluto/rea：周增星 +10 万量级，疑似刷星；逆向类工具，来路不明二进制不运行。
- Ebony-Vinyl/dsh-our-free-model：宣称免 Key 不限量用前沿模型，数据路径不透明，不装、不用它处理任何业务数据。
- storytold/*craft 系列（photocraft/pdfcraft/filmcraft/wordcraft）：同作者批量纯 Rust 复刻，成熟度存疑，不用于真实文件。

## 请 Codex 执行（按顺序，每项先出评估再等确认）

- **任务 A（VoiceStudio 可行性报告）**：读官方 README 与依赖/模型说明，输出：Windows 支持情况、GPU/显存/磁盘需求、模型清单与体积、安装步骤概要、与本地已装 ComfyUI/Ollama 是否冲突。只写报告，不安装。
- **任务 B（HyperFrames 最小样片）**：若本机 Node 环境可用，按官方示例做一个 5–10 秒的 HTML→视频最小样片（内容随意，如品牌名+一句话），记录命令、耗时、产物路径。这项可以直接做。
- **任务 C（PageIndex 示例）**：跑通官方自带示例/样例文档，记录安装量、索引耗时、问答效果截图或原文。不要导入任何 Carter 的业务文档。
- **任务 D（Agent-Reach 风险简报）**：只读官方文档，输出：它如何访问各平台（Cookie/API/抓取）、需要什么凭据、已知的封号/风控讨论。不要登录、不要安装到主环境。

## 结果回流方式

把结果写成一个文件：`codex-tasks/results/2026-10-23-github-picks-results.md`，每个任务一节，结论先行（能用/不能用/待确认），附关键证据（版本号、命令输出摘要、产物路径）。写完后 commit 并 push 回本仓库；Muse 会从仓库读结果并向 Carter 汇总。若 push 失败，把文件留本地并在会话里告诉 Carter 失败原因。

## 红线

- 不使用任何真实客户数据、账号密码、API Key 做测试。
- 不购买、不订阅、不调用付费 API。
- 不登录 Carter 的社交主账号（X/抖音/小红书等）。
- 重型下载（>2GB）或改系统环境前，先在结果文件写方案，等 Carter 确认。
