# Wallbreak · 破壁计划

**Evidence-led Unity reconstruction: executable behavior, verified equivalence, readable source.**

A Codex skill for the stage after Unity assets and code evidence have been extracted. Wallbreak restores how scripts, shaders, initialization, and runtime consumers use that information, then validates the agreed behavior, UI, saves, visuals, and timing against the original.

**中文：基于原包证据，恢复真正生效的 Unity 行为与画面，交付可读、可维护源码。**

Version: **1.0.0** · License: **MIT** · Skill identifier: `unity-semantic-restoration`

## English

### Install

Clone this repository into the existing technical skill name. The repository's public name is `wallbreak`; the folder and frontmatter identifier remain `unity-semantic-restoration` for compatibility.

```sh
git clone https://github.com/NeilXiao233/wallbreak.git "${CODEX_HOME:-$HOME/.codex}/skills/unity-semantic-restoration"
```

If that directory already exists, preserve local changes and update the existing installation; do not install a duplicate alias. Restart Codex or start a new chat so it discovers the current skill. The command above is for POSIX shells; on Windows, clone to the corresponding skills directory in your configured Codex home.

### Invoke

Say **`破壁`**, **`Wallbreak`**, or explicitly invoke **`$unity-semantic-restoration`**. The Chinese trigger matches whenever the user message contains `破壁`; the English name is an explicit invocation alias. A bare trigger in the current recovery project means continue reconstruction. Requests to review, explain, edit the skill, or stop retain that intent; activation does not authorize unrelated actions.

Examples:

- `Wallbreak this Unity project. Preserve the original scenes and verify runtime and visual equivalence.`
- `Review this project's Wallbreak gaps; keep the review read-only.`

### What the skill does

1. Read the current project scope, evidence, authoritative documents, and valid results.
2. Preserve original asset identities and reconstruct the actual runtime graph and dependencies.
3. Recover readable C# and shader semantics: branches, receivers, coordinate spaces, callbacks, and lifecycles.
4. Connect recovered logic to the production consumers and original startup path.
5. Validate each claim at its proper layer and bind source, build, shipped artifact, and runtime evidence.
6. Deliver maintainable source, reproducible instructions, scoped receipts, and explicit remaining gaps.

Unpacking, signatures, stub scripts, a successful build, and a playable first level are intermediate results. The goal is evidence-backed equivalence within an agreed scope, not a claim to recover the author's exact variable names, comments, or repository history.

### Environment and portability

This is a documentation skill, not a decompiler or Unity plugin. It contains no game packages, game source, assets, credentials, private logs, or required reference-session corpus. It requires no fixed local paths, operating system, MCP server, or other skill.

Use available project-appropriate tools. Import/build verification needs a suitable Unity Editor and project dependencies; runtime and visual acceptance need suitable execution and graphics conditions. Static recovery can continue when only those validation layers are unavailable. The skill does not install tools or operate devices automatically.

Advertising and payment SDKs follow the current user's scope. When explicitly excluded, keep narrow completion/success interfaces and required game callbacks rather than blocking the main flow or deleting rewards and result UI.

### Included resources

- [SKILL.md](SKILL.md): activation, execution, and acceptance rules (Chinese).
- [Stages and acceptance](references/stages-and-acceptance.md): inputs, milestones, scoped completion.
- [Code semantics](references/code-semantics.md): evidence, contracts, adapters, readable implementation.
- [Rendering and layout](references/render-and-layout.md): shaders, runtime graph, matched comparisons.
- [Verification and handoff](references/verification-and-handoff.md): proof boundaries, versions, regression, delivery.
- [Case patterns](references/case-lessons.md): anonymized lessons in Chinese and English.
- [agents/openai.yaml](agents/openai.yaml): Codex display and invocation metadata.

The README provides bilingual usage; the detailed execution references are maintained in Chinese. No translations are required at runtime.

### Relationship to Wallfacer

[Wallfacer Reverse](https://github.com/NeilXiao233/wallfacer-reverse) manages evidence continuity and optional handoff state for complex recovery tasks. Wallbreak focuses on executable Unity reconstruction and equivalence. Its release layout follows Wallfacer's skill entrypoint, relative references, UI metadata, bilingual README, versioning, and MIT license. Neither skill requires the other, and Wallbreak does not create a second project state system.

## 中文

### 安装与触发

按上方命令安装到 `unity-semantic-restoration` 目录；已有安装先保留本地改动，再更新，避免双份同名技能。安装后重启 Codex 或新建会话，确保读取当前版本。

用户消息中出现 **「破壁」** 即触发；也可说 **Wallbreak** 或显式使用 **`$unity-semantic-restoration`**。不用说完整的「执行破壁计划」。

- `对当前项目破壁，沿用原工程，继续完成原版等价重建。`
- `审核这个项目的破壁缺口，本轮只读。`

### 目标与流程

适用于 Unity 资源、类型与代码证据已经拿到，但脚本仍为空壳、画面或行为与原版不同的阶段。

**工程图与依赖绑定 → 可执行语义重建 → 正式消费者接入 → 运行与视觉差分验证 → 可维护源码交付。**

保留原场景、Prefab、GUID、材质与配置；按原证据恢复真正执行的分支、字段接收者、坐标空间、回调与生命周期。验证从原启动链进入的玩法、UI、存档、视觉和时序，并关联当前源码、构建、实际包与运行回执。

解包完成、方法签名齐全、能够编译或首关可玩都只是中间成果。完成标准是约定范围内的有效实现、与实际产物匹配的等价证据及可读源码；未知分支明确保留，不以方法数量或构建次数代表完成率。

### 对外发布与解耦

公开包不包含游戏原包、资产、还原源码、私有会话与实验回执。案例已匿名化，仅保留可迁移的方法；技能不依赖本机目录、固定 Unity 版本、特定系统、MCP 或面壁者。

按当前环境选择工具。导入与构建需要匹配目标的 Unity Editor 和依赖；视觉验收需要真实图形条件，缺少时继续独立静态恢复并明确未验证。广告和支付是否排除由当前任务决定；明确排除时保留必要回调，不让 SDK 阻碍主线。

### 与面壁者的关系

面壁者侧重复杂任务的证据连续性与按需交接；破壁计划侧重 Unity 有效语义、原版等价性与可维护源码。参考其发布结构，但两者相互独立。项目既有 README、任务卡和证据仍是事实来源。

## License / 许可证

[MIT](LICENSE). The license covers this skill's documentation and metadata, not third-party games, assets, binaries, or dependencies. / 许可证仅覆盖本技能的文档与元数据，不授予第三方游戏、资产、二进制或依赖的权利。
