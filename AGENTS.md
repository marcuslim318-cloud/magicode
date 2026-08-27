# 魔码学院 MagiCode Academy · Agent 宪法

## 项目定位

- 项目：魔码学院（`magicode`），面向零基础中文用户的 Game-Fi Vibe Coding 训练营网站——一所教你用咒语（提示词）驱使使魔（AI）的魔法学院。
- 技术栈：静态 HTML / CSS / 原生 JS（单文件，无框架、无构建工具、无 npm 依赖）。每个关卡 = 一个独立 `.html`，内联全部样式与脚本。部署至 GitHub Pages（`github.com/marcuslim318-cloud/magicode`）。
- 平台：Windows，PowerShell 5.1。Node 仅用于 `node --check` 语法校验和 impeccable 脚本（`node script.mjs`），不用于构建。

## 真源清单与优先级

事实冲突时按此顺序：

1. 当前源码（`magicode/*.html`）——已部署的活页面是最终真相。
2. 本宪法（`AGENTS.md`）及工具入口文件。
3. `PRODUCT.md`（产品真相源：课程骨架、进度存储语义、品牌承诺、未决清单）。
4. `DESIGN.md`（设计系统真相源：令牌、组件、Do's & Don'ts）。
5. 课程文档（`curriculum/new-work.md` 等，须与 PRODUCT.md 一致）。
6. 历史提交、用户确认。

本仓库**无** dev-docs / ADR / CI / package.json；`.impeccable/` 内为评审快照与截图，不是真源。根目录还住着无关项目 `student-council/`，其文件与本产品互不相干，不得触碰。

## Owner Map（唯一 owner）

- **关卡体验**（每个关卡的所有 UI / 交互 / 状态机 / 进度写入）：`magicode/levelN.html`——每个关卡是独立单文件，自包含全部 CSS 与 JS，不跨文件共享代码。
- **产品真相**（课程骨架、进度存储语义、称号阶梯、世界观映射表、品牌承诺、未决清单）：`PRODUCT.md`。
- **设计系统**（色板、字体、圆角、间距、组件规范、Do's & Don'ts）：`DESIGN.md`。
- **视觉世界身份**（色值、字体栈、✦ 母题、描线 SVG 语法、烛金稀有律）：`DESIGN.md` frontmatter 令牌 + Overview 部分——修改需用户明确确认。
- **进度存储合同**（`magicode.progress.v1` 字段语义、连击算法、XP 入账规则）：`PRODUCT.md` 进度存储章节——所有关卡必须遵守同一合同。
- **世界观术语**（咒语/使魔/无限图书馆/封印卷轴/恶咒/除咒/时间转换器/分身术/显形术）：`PRODUCT.md` 世界观映射表——跨文件引用唯一真源。
- **页面间导航**（← 学院大门、课程地图锚点）：各关卡 HTML 顶栏自行实现，不抽取公共模块。
- **环境变量**：`.env`（已从 git 移除，禁止入库）；GitHub Pages 无服务端环境变量。

## 角色与权限模型（事实）

本项目无认证系统。"权限"是 localStorage 进度门控 + 叙事锁定：

| 关卡 | 门控条件 | XP 奖励 | 产物 |
|------|----------|---------|------|
| 第 0 关（入学通知书） | 无（开放） | +120 | 示意终端施法体验 |
| 第 1 关（封印人生第一卷） | level0Done = true | +150 | 真实 GitHub 仓库 + 第一次 commit |
| 第 2 关（让卷轴生长） | level1Done = true | +180 | 多次 commit + git revert 体验 |
| 第 3 关（铭刻石碑·第一章收官） | level2Done = true | +210 | 用咒语给已有仓库加三处真实改动 + 晋升「施咒学徒」 |
| 第 4 关（点亮地图·第二章首关） | level3Done = true | +240 | 从零做一个能发出去的网页并部署到 GitHub Pages，存 siteUrl |
| 第 5 关（点亮永生灯·让作品活过来） | level4Done = true | +270 | 用咒语给线上网页加三种真实交互（按钮/切换/计数），让作品活起来 |
| 第 6 关（校准星空罗盘·让作品看世界） | level5Done = true | +300 | 用咒语给线上网页接上真实世界的数据（名言/实时数字/时钟） |
| 第 7 关（披上星光长袍·让作品好看） | level6Done = true | +330 | 用咒语给线上作品换三套皮肤（配色/字体/布局），让页面真正好看 |
| 第 8 关（点亮陈列殿堂·第二章收官） | level7Done = true | +360 | 做一个个人主页/作品门面，把自己一路做的作品陈列给世界 |
| 第 9 关（举起护法镜·黑魔法防御课首关） | level8Done = true | +390 | 面对并修复第一道真实 bug（报错），学会贴给 AI 除咒 |
| 第 10 关（倒转时光沙漏·安全可回溯） | level9Done = true | +420 | 用 git revert 安全回到好状态，改坏也能一键回溯 |
| 第 11 关（透过冰晶棱镜·安全加分身） | level10Done = true | +450 | 用分支（分身术）安全试新功能，好了再合并回主线 |
| 第 4–12 关 | 前一关完成 | 待定 | 待设计 |

- 称号按**章**晋升，不是按关：第 0 关起称「收信人」；第一章（关卡 1–3）全通后晋升「施咒学徒」。
- 连击（streak）只按「魔力值入账的日子」累计——纯重玩不增不减、不清零。

## 非目标与拒绝方向

- **禁止**引入前端框架（React / Vue / Svelte / Alpine 等）：单文件 HTML 是架构承诺，不是权宜之计。
- **禁止**引入构建工具（Vite / Webpack / esbuild / Tailwind 等）：样式内联在每个文件的 `<style>` 块中。
- **禁止**引入 npm 依赖：每个 `.html` 是零依赖自包含文件。
- **禁止**引入后端 / API / 数据库 / 认证系统：纯静态站点，进度存 localStorage。
- **禁止**引入 TypeScript：所有脚本为原生 JS，用 `node --check` 校验语法。
- **禁止**把多个关卡合并成单页应用（SPA）：每个关卡是独立文件，可单独分享链接。
- **禁止**修改已发布关卡的世界观身份（色值、字体栈、✦ 母题、描线 SVG 语法）而不经用户确认。
- **禁止**用 emoji 替代描线 SVG 图标（✦ 母题和已建立的造物除外）。
- **禁止**用硬偏移阴影（`box-shadow: 4px 4px 0`）、渐变文字、玻璃模糊装饰。
- **禁止**用等宽字体排正文散文——等宽只出现在机器说话的地方（终端、数据、标签）。
- **禁止**在示意性终端中伪装真实命令行——必须标注「示意演示」。
- 不为了速度跳过教学验证：每关必须有真实操作形态（外链引导 + 贴链接验收）。
- 不为了速度删除进度存储、连击、称号、分享功能——它们是品牌承诺的一部分。

## 必需工作流

```text
课程大纲审查 → 视觉世界确认（DESIGN.md 令牌） → 概念发牌（concept-seed）
  → 结构选择（serve-question 或结构化提问） → 核心实现（单文件 HTML）
  → 语法校验（node --check） → 反模式检测（detect.mjs） → 浏览器实测
  → 降级 finish review → DESIGN.md 组件补录 → git 边界复核
```

- 半路接管：先只读审计已有关卡的进度存储语义和世界令牌一致性，禁止把已有页面当空文件重写。
- 编码前推理闸：这一关教什么？操作形态是什么（纯浏览器 / 外链引导）？进度存储新增哪些字段？世界令牌是否复用？最大回归风险（进度合同断裂 / 世界身份漂移）？
- 跨关卡复用的语义（进度存储格式、XP 规则、术语映射）必须以 `PRODUCT.md` 为真源，不散落在各 HTML 的注释中。
- 每个新关卡必须携带 impeccable direction contract 注释（THESIS / OWN-WORLD / STORY / FIRST VIEWPORT / FORM / FINISH），FORM 中必须包含 concept-seed 的 key。

## 命令与验收

| 命令 | 用途 | 说明 |
|------|------|------|
| `node --check <file>` | JS 语法校验 | 改动后**必须**通过 |
| `node .../scripts/detect.mjs <file>` | 反模式检测 | 0 anti-patterns 为通过；em-dash advisory 为已知中文误报 |
| `node .../scripts/concept-seed.mjs --scope surface --mode operate` | 概念发牌 | 新关卡结构选型时使用 |
| 浏览器实测 | 关卡功能验证 | 每关须验证：首次访问、完成流程、毕业生重访、未解锁状态 |
| GitHub Pages 部署 | 生产发布 | 仅用户明确要求时执行 `git push` |

- 项目**无** typecheck / unit test / e2e / lint 脚本——不得虚构或假装这些命令存在。
- 验收强度：任何代码改动 = `node --check` 通过 + `detect.mjs` 0 反模式 + 浏览器实测关键路径（首次访问 / 完成流程 / 毕业生重访 / 锁定状态）。进度存储改动 = 跨关卡字段一致性检查。
- 世界身份漂移、进度合同断裂、示意终端未标注、`prefers-reduced-motion` 缺失，按缺陷处理，不得带着声称完成。

## 实现规则

- 从 `DESIGN.md`（世界令牌）和 `PRODUCT.md`（课程目标、进度合同）开始，不从 UI 倒推核心。
- 每个关卡是独立单文件（`<style>` + `<script>` 内联），不抽取公共 CSS/JS 模块——文件间不共享代码。
- 复用世界令牌（`--ink` / `--gold` / `--text` / `--text-dim` / `--text-faint` / `--line` / `--line-strong` / `--gold-soft` / `--radius-card` / `--font-sans` / `--font-mono`）时保持值完全一致，不微调。
- 每个关卡必须携带 impeccable direction contract 注释（`<!-- impeccable direction contract ... -->`）。
- 示意性终端（term-strip / term-bar）必须标注「示意演示」，不得伪装成真实命令行。
- 每个动效必须过 `prefers-reduced-motion` 闸门；签名缓动 `cubic-bezier(0.16, 1, 0.3, 1)`。
- JS 才能显示的内容用 `.js` 类作用域隐藏（`<head>` 内联脚本 `document.documentElement.classList.add("js")`），保证无 JS 时 noscript 内容可见。
- 用户可见文案统一简体中文，世界观术语遵循 `PRODUCT.md` 映射表。
- OG meta 标签：每个关卡须有 `og:site_name` / `og:title` / `og:description` / `og:type` / `og:locale` / `twitter:card`（共 6 条）。
- 错误/异常状态用诚实文案呈现（如「这不像一条图书馆的地址」），不静默吞掉。
- 进度存储字段变更必须同步 `PRODUCT.md` 进度存储章节。

## Git 规则

- 提交前确认 `git status --short`；**禁止 `git add .`**，只 stage 本任务相关文件。
- 提交信息用中文，格式：`第 N 关「关卡名」：核心改动摘要`。
- dirty worktree 中不得回滚、覆盖或吸入用户未授权的改动。
- 破坏性 git 命令（`git reset` / `git push --force`）须用户明确确认。
- 部署推送仅在用户明确要求时执行。

## 必须停止并询问

- 课程大纲、设计系统、品牌承诺互相冲突。
- 需要删除已发布关卡的文件或改动其已发布行为。
- 需要修改世界观身份（色值、字体栈、✦ 母题、描线 SVG 语法）。
- 需要改变课程教学目标（每关教什么、操作形态、验收标准）。
- 需要引入新依赖、新框架、新构建工具。
- 上下文不足以判断进度合同影响范围，且猜测会造成跨关卡回归。
- 停止时必须给出：冲突证据、推荐方向、需要用户确认的问题——不能只说「无法继续」。

## 交接规则

上下文过大、换窗口或交给另一 agent 时，必须产出可复制交接文本：

1. 当前目标与边界（正在做第几关、选用的结构卡、concept-seed key）
2. git 状态与已改文件（`git status --short` + `git log --oneline -3`）
3. 已完成工作与验收结果（`node --check` / `detect.mjs` / 浏览器实测结论）
4. 未闭合风险（进度合同字段是否已同步 PRODUCT.md、世界身份是否有漂移）
5. 下一步最安全命令与停止条件
