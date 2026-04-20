# Offer 准备官

> 一个用于求职准备的完整 skill：先判断值不值得投、再审计证据、再改简历、出讲稿、生成面试题库、做高压模拟面试。

[中文](#中文) | [English](#english)

---

## 中文

### 这是什么？

`Offer 准备官` 是一个面向求职场景的完整 skill。  
它不是“简历润色工具”，而是一条完整的准备链路：

`岗位匹配判断 -> 证据审计 -> 简历定制 -> 项目讲稿 -> 面试题库 -> 模拟面试`

它适合这些情况：

- 你拿到一个 JD，先想知道值不值得认真投
- 你不想为了过筛写过头，想先搞清楚自己到底能写什么
- 你有多个项目，不知道应该主打哪个
- 你想把简历内容变成能在面试里讲得出来、守得住的答案
- 你想先系统练题，再进入高压追问

默认执行骨架是：

`输入判断 -> 读取最小必要材料 -> 证据分类 -> 决策/策略 -> 具体模块输出`

### 有哪些功能？

| 功能 | 作用 | 典型输出 |
| --- | --- | --- |
| `岗位匹配判断` | 拆 JD、判断匹配度和投递风险 | `JD 审计`、`Go / No-Go` |
| `简历定制` | 基于证据重写简历，不靠硬包装 | 项目排序、定制 bullet、缺口提醒 |
| `项目叙事重构` | 从岗位视角重组项目故事 | 简历版叙事、口述版叙事 |
| `项目讲稿` | 生成可防守的长答 / 短答 | 中文长答、短答、追问、风险提醒 |
| `面试题库生成` | 直接输出系统练习题库 | `简历深挖题 / JD 场景题 / JD 专业能力题` |
| `模拟面试` | 高压追问、纠偏、保守改写 | 单题追问、复盘、保守回答 |

### 这个 skill 的核心特点

它有三个明显区别：

1. 先判断 `值不值得投`，而不是默认开始包装
2. 先区分 `直接证据 / 间接证据 / 缺失证据 / 禁止声称`
3. 题库和模拟面试都会回指“最容易答崩、最容易答过头”的点

### 它不会做什么？

- 凭空补造你没做过的经历、实验、框架经验
- 把 `间接证据` 包装成 `直接证据`
- 保证你一定过 ATS 或一定拿到 offer
- 默认生成通用八股题或行为题题库
- 在环境不支持时假装已经写入本地文件或生成 `.docx`

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

### 怎么使用？

推荐按这个顺序：

1. 填个人档案
2. 录入简历母版
3. 录入项目材料
4. 给目标 JD，先做岗位匹配判断
5. 再决定下一步：
   - 改简历
   - 出项目讲稿
   - 生成面试题库
   - 做模拟面试

### 常用调用方式

#### 1. 先判断值不值得投

```text
这是目标 JD，先帮我判断值不值得认真投：[粘贴 JD]
```

#### 2. 针对 JD 改简历

```text
这是目标 JD，基于我现有材料帮我改简历：[粘贴 JD]
```

#### 3. 生成项目讲稿

```text
这是目标 JD，帮我生成项目讲稿，重点准备最可能被追问的项目
```

#### 4. 直接生成题库

```text
这是目标 JD 和我的材料，帮我生成一套面试题库
按这 3 组输出：简历深挖题 / JD 场景题 / JD 专业能力题
每题都附出题意图和高风险回答提醒
```

#### 5. 进入高压模拟面试

```text
基于这个 JD 和我的项目，帮我做一轮高压模拟面试
```

### 面试题库长什么样？

题库固定分 3 组：

1. `简历深挖题`
2. `JD 场景题`
3. `JD 专业能力题`

默认每组 `6` 题，总共 `18` 题。  
每道题都包含：

- `题目`
- `出题意图 / 考察点`
- `高风险回答提醒`

注意：

- 不出通用八股题
- 不出行为题
- 不默认给参考答案
- 如果你想针对某一题继续练，可以直接进入模拟面试

这里的边界是：

- `题库` 默认不出行为题，因为题库阶段追求的是高信噪比、强贴岗、强贴证据
- `模拟面试` 仍然支持 `BQ`，因为 mock 阶段的目标是练临场表达、追问承压和保守回答
- 所以“不出行为题”只约束题库，不代表整个 skill 不支持行为面试

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

### 真实性与护栏

这个 skill 的一个核心原则是：**宁可少写，不要写虚。**

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

另外，项目文件录入默认生成的是“可直接保存的 markdown 草稿”。
只有在当前运行环境真的支持文件写入，而且用户明确要求保存时，才应该直接写入本地文件。

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
It is not just a resume-polishing tool. It supports a full workflow:

`Role Fit Check -> Evidence Audit -> Resume Tailoring -> Pitch Scripts -> Interview Question Bank -> Pressure Interview`

It is useful when:

- you want to know whether a JD is worth serious effort
- you want to know what you can honestly claim before tailoring
- you have multiple projects and need to decide which ones should lead
- you want interview-ready answers, not just prettier bullets
- you want a structured question bank before entering a live mock interview

Its default execution skeleton is:

`Input triage -> Minimal material reading -> Evidence classification -> Decision/strategy -> Output module`

### Core features

| Feature | What it does | Typical output |
| --- | --- | --- |
| `Role Fit Check` | evaluates the JD and the risk of applying | JD audit + Go / No-Go |
| `Resume Tailoring` | rewrites from evidence, not from wishful matching | tailored bullets + gap warnings |
| `Narrative Reframing` | reframes a project from a target-role angle | resume version + spoken version |
| `Pitch Scripts` | generates defendable interview answers | long/short answers + likely follow-ups |
| `Interview Question Bank` | outputs a structured question set for practice | 3 groups of questions + intent + risk notes |
| `Pressure Interview` | stress-tests whether your story survives pushback | one-question follow-up + safer answer |

### What this skill does not do

- invent missing experience
- turn indirect evidence into direct claims
- guarantee ATS pass or offer outcomes
- default to generic behavioral question banks
- pretend it saved files or generated `.docx` when the runtime cannot do that

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

### Example usage

```text
Here is the JD. First tell me whether this role is worth targeting.
```

```text
Based on this JD and my materials, tailor my resume.
```

```text
Generate an interview question bank from this JD and my projects.
Group it into resume deep-dive / JD scenario / JD capability questions.
```

```text
Take question 4 from the question bank and run a high-pressure mock interview.
```

### Guardrails

This skill is designed to protect truthfulness:

- it distinguishes direct, indirect, missing, and do-not-claim evidence
- it does not invent experience
- it should refuse requests to fabricate claims and switch to safer phrasing

Project intake should default to generating a save-ready Markdown draft.
Direct file writes should only happen when the runtime supports them and the user explicitly asks for them.

### Notes

- richer materials lead to stronger outputs
- without a JD, the question bank can only fully support resume deep-dive questions
- the first version of the question bank does not generate reference answers
- behavioral questions are excluded from the default question bank, but still supported in mock interview mode
- `.docx` generation and local file writes are runtime-dependent capabilities
