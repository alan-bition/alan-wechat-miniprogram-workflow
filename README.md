# alan-wechat-miniprogram-workflow

一个面向原生微信小程序的完整开发工作流 Skill，覆盖需求梳理、原型与 UI 审查、WXML/WXSS 实现、本地 Docker 联调、测试，以及预览版和体验版交付。

A practical workflow skill for building and shipping native WeChat Mini Programs with a real backend and local Docker development. It covers requirements, prototype and UI review, WXML/WXSS implementation, local validation, and preview or experience-version delivery.

## 中文说明

### 适用范围

适用于：

- 从零开发微信原生小程序；
- 接手已有小程序并继续迭代；
- 局部页面、交互或接口修复；
- 使用真实后端与本地 Docker 数据库进行联调；
- 准备预览、体验版或审核候选版本。

Skill 会尊重已有 PRD、原型、设计规范、技术栈和用户限定的交付阶段，不会因为用户提出开发请求就自动部署、提审或发布。

### 主要流程

1. 梳理目标用户、核心场景、业务规则、权限和验收标准；
2. 生成或检查 PRD、HTML 原型和页面状态；
3. 审查现有体验，并在需要时接入 `audit`、`ui-ux-pro-max`、`design-system`、`ui-styling` 和 `image-to-code`；
4. 将确认后的视觉方向转换为原生 WXML、WXSS、TypeScript 和组件实现；
5. 使用真实后端、Prisma 和本地 Docker 数据库完成联调；
6. 执行类型检查、业务测试、页面检查、视觉对照和真机验证；
7. 区分本地预览、开发版、体验版、提交审核和正式发布，按用户授权推进。

### 安装

将整个 Skill 文件夹放入用户级或项目级 Skill 目录：

```text
~/.agents/skills/alan-wechat-miniprogram-workflow/
项目目录/.agents/skills/alan-wechat-miniprogram-workflow/
```

不要只复制 `SKILL.md`，参考资料、模板和元数据需要一起保留。

### 调用示例

```text
使用 $alan-wechat-miniprogram-workflow，帮助我开发一个微信小程序。先梳理需求并生成 PRD 和原型，本轮仅本地开发，不上传。
```

已有页面改版、从零开发和局部修复会采用不同入口；纯后端修复不强制启动完整设计流程。若明确要求使用某个外部 Skill 且该 Skill 缺失，会暂停依赖它的阶段并说明原因；可选依赖缺失时会回退到内置流程并记录实际情况。

### 目录结构

```text
SKILL.md                    # 主流程、触发条件、边界和验收要求
agents/openai.yaml          # Skill 元数据和默认调用提示
references/                 # 工作流、设计协作、测试、版本交付和微信常见问题
assets/templates/           # PRD、原型、设计、开发、测试、审查和设计 QA 模板
LICENSE                     # MIT 许可证
```

### 原生小程序适配原则

本 Skill 以 WXML、WXSS、TypeScript 和现有小程序工程为实现基准。外部设计 Skill 的网页示例只用于分析和设计建议，不会自动引入 React、Tailwind、shadcn、GSAP 或重建工程。视觉复核应使用微信开发者工具或真机截图，并记录尺寸、数据和状态。

## English

### Scope

Use this skill to:

- build a native WeChat Mini Program from scratch;
- take over and extend an existing Mini Program;
- fix a focused page, interaction, or API issue;
- connect a real backend to a local Docker database;
- prepare a preview, experience version, or review candidate.

The skill respects existing PRDs, prototypes, design decisions, technology choices, and the delivery boundary stated by the user. A development request does not automatically authorize deployment, review submission, or production release.

### Workflow

1. Clarify users, core scenarios, business rules, permissions, and acceptance criteria.
2. Create or inspect the PRD, HTML prototype, and page states.
3. Audit the existing experience and, when appropriate, use `audit`, `ui-ux-pro-max`, `design-system`, `ui-styling`, and `image-to-code`.
4. Convert the approved visual direction into native WXML, WXSS, TypeScript, and component implementation.
5. Integrate the real backend, Prisma, and a local Docker database.
6. Run type checks, business tests, page checks, visual comparison, and device validation.
7. Keep local preview, development build, experience version, review submission, and production release separate, and advance only within the user's authorization.

### Installation

Copy the complete Skill directory into a user-level or project-level Skill directory:

```text
~/.agents/skills/alan-wechat-miniprogram-workflow/
project/.agents/skills/alan-wechat-miniprogram-workflow/
```

Keep `SKILL.md`, references, templates, and metadata together; do not install only the main file.

### Invocation example

```text
Use $alan-wechat-miniprogram-workflow to help me develop a WeChat Mini Program. Start by organizing the requirements and generating the PRD and prototype. This round is local development only; do not upload.
```

The skill has separate entry rules for redesigning an existing page, starting a greenfield project, and making a focused fix. A backend-only fix does not require the full design workflow. If a user explicitly requires a missing external skill, the dependent stage pauses with a clear explanation; optional missing dependencies fall back to the built-in workflow and are recorded.

### Native implementation principles

The implementation baseline is the existing native Mini Program stack: WXML, WXSS, TypeScript, and the current project structure. Web examples from design skills are used for analysis and visual direction only; they do not trigger React, Tailwind, shadcn, GSAP, or a project rebuild. Visual QA should use screenshots from the WeChat DevTools or a real device with matching viewport, data, and state.

## License / 许可证

MIT. See [`LICENSE`](LICENSE).
