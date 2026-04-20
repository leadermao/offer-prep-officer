# Offer 准备官

> 一个面向求职准备的完整 skill：先判断这个岗位值不值得投，再审计你到底能写什么，最后才进入简历、讲稿、题库和高压模拟面试。

[中文](#中文) | [English](#english)

---

## 中文

### 这是什么？

`Offer 准备官` 是一个面向求职场景的完整 skill。

它不是“简历润色工具”，也不是“帮你多包装一点”的求职助手。
它更像一个**受真实性约束的投递决策与面试准备 skill**：

`岗位匹配判断 -> 证据审计 -> Go / No-Go -> 简历定制 -> 项目讲稿 -> 面试题库 -> 高压模拟面试`

它适合这些情况：

- 你拿到一个 JD，先想知道值不值得认真投
- 你不想为了过筛写过头，想先搞清楚自己到底能写什么
- 你有多个项目，但不知道哪个应该主打、哪个应该降权
- 你不只想把简历写好看，还想让它在面试里讲得出来、守得住
- 你想先系统练题，再进入高压追问

默认执行骨架是：

`输入判断 -> 读取最小必要材料 -> 证据分类 -> 决策 / 策略 -> 具体模块输出`

### 它和一般“求职 copilot”有什么不同？

这个 skill 的重点不是“生成更多内容”，而是**先做约束，再做输出**。

它有三个核心特点：

1. **先判断值不值得投**
   不默认开始包装，而是先拆 JD、识别硬门槛、给出 `Go / Go with Caveats / No-Go`
2. **先区分证据，再决定怎么写**
   所有改写都建立在四类证据之上：
   - `直接证据`
   - `间接证据`
   - `缺失证据`
   - `禁止声称`
3. **题库和模拟面试会回指高风险点**
   不是泛泛出题，而是围绕“最容易答崩、最容易答过头、最容易被追问击穿”的位置来练

### 它不会做什么？

- 凭空补造你没做过的经历、实验、框架经验
- 把 `间接证据` 包装成 `直接证据`
- 因为“先过筛再说”就帮你伪造项目 ownership
- 保证你一定过 ATS 或一定拿到 offer
- 默认生成通用八股题或行为题题库
- 在环境不支持时假装已经写入本地文件或生成 `.docx`

### Inspiration

This project is inspired by `spontaneousai/job-hunt-copilot`.

但它没有沿用“素材库存好 -> 直接按岗位生成”的默认逻辑，
而是把重点前移到了：

- `先判断值不值得投`
- `先做证据审计`
- `先限制不能怎么写`
- `再进入定制输出和模拟面试`

也就是说，它更关注：

**是否匹配、是否真实、是否能守住。**

### 有哪些功能？

| 功能 | 作用 | 典型输出 |
| --- | --- | --- |
| `岗位匹配判断` | 拆 JD、识别硬门槛、判断投递风险 | `JD 审计`、`Go / No-Go` |
| `证据审计` | 把候选材料映射为四类证据 | `Evidence Matrix`、风险提醒 |
| `简历定制` | 基于证据重写简历，而不是靠硬包装 | 定制 bullet、项目排序、缺口提醒 |
| `项目叙事重构` | 从目标岗位视角重组项目故事 | 简历版叙事、口述版叙事 |
| `项目讲稿` | 生成可防守的长答 / 短答 | 中文长答、短答、追问、风险提醒 |
| `面试题库生成` | 输出系统练习题库 | `简历深挖题 / JD 场景题 / JD 专业能力题` |
| `模拟面试` | 高压追问、纠偏、保守改写 | 单题追问、复盘、保守回答 |
| `项目文件录入` | 把散乱项目经验整理成可复用素材 | 结构化 markdown 草稿 |

### 推荐怎么用？

不是必须先手填 `self_profile` 和 `resume_base`。

更准确的说法是：

- **最完整的用法**：先整理 `self_profile`、`resume_base` 和项目材料，再持续复用
- **够用的用法**：直接给 `JD + 简历 + 1-2 个重点项目`
- **最低限度的用法**：只给 `JD`，先做岗位匹配判断和初步 `Go / No-Go`

如果你打算长期用这个 skill，推荐按这个顺序准备材料：

1. 填 `self_profile`
2. 填 `resume_base`
3. 录入项目材料
4. 给目标 JD，先做岗位匹配判断
5. 再决定下一步是：
   - 改简历
   - 出项目讲稿
   - 生成面试题库
   - 做模拟面试

### 最常见的用法

#### 1）先判断值不值得投

```text
这是目标 JD，先帮我判断值不值得认真投：[粘贴 JD]
```

#### 2）先做证据审计，再改简历

```text
这是目标 JD，先做证据审计，再基于我现有材料帮我改简历：[粘贴 JD]
```

#### 3）生成项目讲稿

```text
这是目标 JD，帮我生成项目讲稿，重点准备最可能被追问的项目
```

#### 4）直接生成题库

```text
这是目标 JD 和我的材料，帮我生成一套面试题库
按这 3 组输出：简历深挖题 / JD 场景题 / JD 专业能力题
每题都附出题意图和高风险回答提醒
```

#### 5）进入高压模拟面试

```text
基于这个 JD 和我的项目，帮我做一轮高压模拟面试
```

### 题库和模拟面试的边界

题库固定分 3 组：

1. `简历深挖题`
2. `JD 场景题`
3. `JD 专业能力题`

默认每组 `6` 题，总共 `18` 题。  
每道题都包含：

- `题目`
- `出题意图 / 考察点`
- `高风险回答提醒`

默认规则：

- 不出通用八股题
- 不出行为题题库
- 不默认给参考答案

这里的边界是：

- `题库` 默认不出行为题，因为题库阶段追求的是**高信噪比、强贴岗、强贴证据**
- `模拟面试` 仍然支持 `BQ`，因为 mock 阶段的目标是**练临场表达、追问承压和保守回答**

所以，“不出行为题”只约束题库，不代表整个 skill 不支持行为面试。

### 真实性与护栏

这个 skill 的核心原则是：

> **宁可少写，不要写虚。**

它会显式区分：

- `直接证据`
- `间接证据`
- `缺失证据`
- `禁止声称`

它不会：

- 把弱证据写成强证据
- 凭空编造你没做过的技能、实验、框架经验
- 因为你要求“先过筛再说”就帮你补造没做过的经历

当用户明确要求编造、补写、伪装未做过经历时，它应该直接拒绝，并转向保守替代表达。

另外，项目文件录入默认生成的是**可直接保存的 markdown 草稿**。
只有在当前运行环境真的支持文件写入，而且用户明确要求保存时，才应该直接写入本地文件。

### 安装方式

这个 skill 优先适配 `Claude Code / Codex` 风格的本地 skill 目录。
其他环境也可以复用这套结构，但 `.docx` 输出、文件写入等能力是否可用，取决于运行环境本身。

#### 方式 1：Claude Code

把 `offer-prep-officer/` 目录复制到 `~/.claude/skills/`：

```bash
mkdir -p ~/.claude/skills
cp -R offer-prep-officer ~/.claude/skills/
```

如果你手上只有 `SKILL.md` 和 `resources/`，也可以按文件复制：

```bash
mkdir -p ~/.claude/skills/offer-prep-officer
cp SKILL.md ~/.claude/skills/offer-prep-officer/SKILL.md
cp -R resources ~/.claude/skills/offer-prep-officer/resources
```

#### 方式 2：Codex

把 `offer-prep-officer/` 目录复制到 `~/.agents/skills/`：

```bash
mkdir -p ~/.agents/skills
cp -R offer-prep-officer ~/.agents/skills/
```

如果你手上只有 `SKILL.md` 和 `resources/`，也可以按文件复制：

```bash
mkdir -p ~/.agents/skills/offer-prep-officer
cp SKILL.md ~/.agents/skills/offer-prep-officer/SKILL.md
cp -R resources ~/.agents/skills/offer-prep-officer/resources
```

#### 方式 3：Claude Skills 安装包

也可以直接使用 `.skill` 包：

`offer-prep-officer.skill`

如果你的运行环境支持 `.skill` 上传，直接上传这个文件即可。

### 示例

下面是一个**虚构示例**，不是任何真实用户经历。

#### 示例候选人

一位做过在线教育产品增长分析和推荐优化的数据科学候选人，最近想投：

- `用户增长算法工程师`
- `推荐策略分析师`

#### 示例 JD

岗位重点包括：

- 基于用户行为数据做用户分层
- 提升转化率与留存
- 优化推荐策略
- 评估策略效果并持续迭代

#### 示例调用 1：岗位匹配判断

```text
这是目标 JD，先告诉我值不值得认真投
```

可能输出：

- 这个岗位更偏增长算法，不是泛数据分析岗
- 你在推荐优化和增长分析上有直接证据
- 你在实验设计上的证据偏弱，面试里要小心

#### 示例调用 2：面试题库

```text
根据这个 JD 和我的项目，生成一套面试题库
```

可能输出片段：

**简历深挖题**
- 题目：你提到推荐策略优化提升了点击率，这个点击率的口径是什么？
- 出题意图 / 考察点：考察你是否真的理解项目指标，而不是只会背结果。
- 高风险回答提醒：不要只报数字，不解释指标定义和上下文。

**JD 场景题**
- 题目：如果推荐点击率提升了，但留存下降，你会先排查什么？
- 出题意图 / 考察点：考察你对业务目标冲突和指标优先级的理解。
- 高风险回答提醒：不要只说“继续调模型”，要先说明你会怎么定义问题。

**JD 专业能力题**
- 题目：在用户分层任务里，你会怎么判断特征工程和模型复杂度的取舍？
- 出题意图 / 考察点：考察你是否理解岗位要求里的专业判断能力。
- 高风险回答提醒：不要只报模型名，不解释为什么这样选。

#### 示例调用 3：继续深练某一题

```text
针对题库里的第 3 题，帮我做一轮高压追问
```

### 注意事项

- 素材越完整，判断和输出越准
- 没有 JD 时，题库只能完整覆盖 `简历深挖题`
- 如果要英文版或双语版，请显式说明
- 第一版题库不输出参考答案，避免用户直接背模板
- `.docx` 输出和本地文件写入属于环境相关能力，不保证所有 runtime 都支持

---

## English

### What is this?

`Offer 准备官` is a complete skill for job application prep.

It is not just a resume-polishing tool, and it is not a "package me a bit harder" job copilot.
It is better understood as a **truth-constrained application decision and interview prep skill**:

`Role Fit Check -> Evidence Audit -> Go / No-Go -> Resume Tailoring -> Pitch Scripts -> Interview Question Bank -> Pressure Interview`

It is useful when:

- you want to know whether a JD is worth serious effort
- you want to know what you can honestly claim before tailoring
- you have multiple projects and need to decide which ones should lead and which ones should be downgraded
- you want more than prettier bullets, and need stories you can actually defend in interviews
- you want a structured question bank before entering a live mock interview

Its default execution skeleton is:

`Input triage -> Minimal material reading -> Evidence classification -> Decision / strategy -> Output module`

### How is it different from a generic job copilot?

This skill is not centered on "generating more output".
It is centered on **adding constraints before output**.

It has three defining traits:

1. **It decides whether the role is worth pursuing first**
   It does not default to packaging. It first breaks down the JD, identifies hard gates, and gives `Go / Go with Caveats / No-Go`.
2. **It classifies evidence before deciding how to write**
   All rewriting is grounded in four evidence types:
   - `direct evidence`
   - `indirect evidence`
   - `missing evidence`
   - `do-not-claim`
3. **Its question bank and mock interview both point back to high-risk failure points**
   The goal is not generic practice. The goal is to train around the places most likely to collapse under follow-up questioning.

### What this skill does not do

- invent missing experience
- turn indirect evidence into direct claims
- fabricate project ownership just because you want to "get through screening first"
- guarantee ATS pass or offer outcomes
- default to generic behavioral question banks
- pretend it saved files or generated `.docx` when the runtime cannot do that

### Inspiration

This project is inspired by `spontaneousai/job-hunt-copilot`.

The difference is where the center of gravity sits.

Instead of defaulting to "store materials, then generate role-specific output", this skill moves the focus earlier:

- decide whether the role is worth pursuing
- audit evidence first
- constrain what must not be claimed
- then enter resume tailoring, scripts, question banks, and mock interviews

In short, it is more concerned with:

**fit, truthfulness, and defensibility.**

### Core features

| Feature | What it does | Typical output |
| --- | --- | --- |
| `Role Fit Check` | evaluates the JD and the risk of applying | JD audit + Go / No-Go |
| `Evidence Audit` | maps candidate materials into evidence classes | Evidence matrix + risk warnings |
| `Resume Tailoring` | rewrites from evidence, not from wishful matching | tailored bullets + gap warnings |
| `Narrative Reframing` | reframes a project from a target-role angle | resume version + spoken version |
| `Pitch Scripts` | generates defendable interview answers | long/short answers + likely follow-ups |
| `Interview Question Bank` | outputs a structured question set for practice | 3 groups of questions + intent + risk notes |
| `Pressure Interview` | stress-tests whether your story survives pushback | one-question follow-up + safer answer |
| `Project Intake` | turns scattered project material into reusable structured notes | save-ready markdown draft |

### Recommended workflow

You do **not** have to fill `self_profile` and `resume_base` before you can use the skill.

A more accurate way to think about usage is:

- **Full setup**: prepare `self_profile`, `resume_base`, and project files for repeated use
- **Good-enough setup**: give `JD + resume + 1-2 key projects`
- **Minimum setup**: give only the `JD` and ask for an initial fit check and `Go / No-Go`

If you plan to use the skill continuously, the recommended preparation order is:

1. fill `self_profile`
2. fill `resume_base`
3. add project materials
4. provide the target JD and run the role fit check first
5. then choose whether to:
   - tailor the resume
   - generate project scripts
   - build the interview question bank
   - run a pressure mock interview

### Common usage

```text
Here is the JD. First tell me whether this role is worth targeting.
```

```text
Here is the JD. Audit the evidence first, then tailor my resume based on what I can honestly claim.
```

```text
Here is the JD. Generate project scripts for the projects most likely to be challenged in interviews.
```

```text
Here is the JD and my materials. Generate an interview question bank grouped into resume deep-dive / JD scenario / JD capability questions.
```

```text
Based on this JD and my projects, run a high-pressure mock interview.
```

### Question bank vs mock interview

The question bank is fixed into 3 groups:

1. `resume deep-dive`
2. `JD scenario`
3. `JD capability`

By default it generates `6` questions per group, `18` in total.
Each question includes:

- `question`
- `intent / what it tests`
- `high-risk answer warning`

Default rules:

- no generic trivia-style questions
- no default behavioral question bank
- no default answer key

The boundary is:

- the `question bank` excludes behavioral questions by default because that stage is optimized for **high signal, high JD relevance, and strong evidence alignment**
- the `mock interview` still supports `BQ` because that stage is optimized for **live delivery, pressure handling, and safer answers under follow-up**

So "no behavioral questions" applies to the default question bank, not to the whole skill.

### Guardrails

This skill is built around one core rule:

> **Write less if needed, but do not write fiction.**

It explicitly distinguishes:

- `direct evidence`
- `indirect evidence`
- `missing evidence`
- `do-not-claim`

It does not:

- upgrade weak evidence into strong claims
- invent skills, experiments, frameworks, or ownership the user did not actually have
- fabricate experience just because the user wants to "clear screening first"

When a user explicitly asks to invent or disguise experience, it should refuse and switch to safer alternatives.

Project intake should default to producing a **save-ready markdown draft**.
Direct file writes should happen only when the runtime supports them and the user explicitly asks for them.

### Installation

This skill works best with Claude Code / Codex style local skill directories.
Environment-specific abilities such as `.docx` generation or direct file writes depend on the runtime you use.

#### Claude Code

Install the skill directory under `~/.claude/skills/`:

```bash
mkdir -p ~/.claude/skills
cp -R offer-prep-officer ~/.claude/skills/
```

#### Codex

Install the skill directory under `~/.agents/skills/`:

```bash
mkdir -p ~/.agents/skills
cp -R offer-prep-officer ~/.agents/skills/
```

#### `.skill` package

You can also use the packaged file directly:

`offer-prep-officer.skill`

Use that file in environments that support `.skill` uploads directly.

### Notes

- richer materials lead to stronger outputs
- without a JD, the question bank can only fully support resume deep-dive questions
- the first version of the question bank does not generate reference answers
- behavioral questions are excluded from the default question bank, but still supported in mock interview mode
- `.docx` generation and local file writes are runtime-dependent capabilities
