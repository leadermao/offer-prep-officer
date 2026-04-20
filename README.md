# Offer 准备官 (Offer Prep Officer)

> Write less if needed, but do not write fiction.
>
> 一个主打“反幻觉、重防守”的求职 Skill。不帮你瞎编简历，只帮你认清现实、定制策略、扛住高压面试。

[中文](#中文) | [English](#english)

---

## 中文

### 怎么用？

#### 把 JD 和经历扔给我，你能得到什么？

你不需要提前填写繁琐表单。

直接把：

- 你想投的 `JD`
- 你现在的简历 / 一段项目经历 / 几段工作经历

扔给这个 Skill 就行。

它不会像很多 AI 一样直接吐一版空洞的“彩虹屁简历”，而是会先像一个严格的面试官一样，给你这几类真正有用的东西：

1. **一份“清醒剂”**
   `Go / No-Go` 判断，直接告诉你这个岗位值不值得投入时间，卡点在哪，风险在哪。
2. **一份“防暴雷”清单**
   证据审计，把你的经历拆成：
   - `直接证据`
   - `间接证据`
   - `缺失证据`
   - `禁止声称`
3. **一份防御型简历输出**
   基于证据边界改写简历 bullet，尽量做到“面试官看着不假，你自己讲着不虚”。
4. **一套靶向高压题库**
   不浪费时间在泛泛行为题上，而是围绕你最薄弱、最贴 JD、最容易被追问击穿的地方出题，并附带高危回答提醒。

如果你继续往下用，它还可以继续给你：

- 项目讲稿
- 简历深挖题
- JD 场景题
- JD 专业能力题
- 单题高压追问
- 保守改写建议

---

### 极简工作流

根据你的准备阶段，直接复制下面的 Prompt 去用。

#### 场景一：极速摸底

手里只有 JD，不想浪费感情，先做可行性评估：

```text
这是目标 JD，先帮我判断值不值得认真投：
[粘贴 JD]
```

#### 场景二：进阶定制

确定要投，开始重构材料，先审计证据，再改简历：

```text
这是目标 JD。请先做证据审计，再基于我以下的经历材料帮我定制简历：
[粘贴 JD]

[粘贴经历 / 简历 / 项目]
```

#### 场景三：深度备战

已经进入面试准备期，开始做防守策略和高压训练：

```text
这是目标 JD 和我的简历。
帮我生成 18 道高危面试题库（包含简历深挖题、JD 场景题、JD 专业能力题），
然后继续对我做一轮高压模拟面试。
```

---

### 典型输出

如果你直接提供 `JD + 经历`，最常见的输出顺序是：

1. `JD 审计`
2. `证据盘点`
3. `Go / No-Go`
4. `你能诚实写什么 / 不该写什么`
5. `定制简历` 或 `题库 / 模拟面试`

这不是“先生成一堆内容再想办法圆”，而是：

`先判断 -> 先约束 -> 再输出`

---

### 核心理念与功能矩阵

市面上很多“求职 Copilot”都在做加法：盲目包装、无脑迎合、默认美化。

`Offer 准备官` 更偏防守型流程：**先做约束，再做输出**。

| 阶段 | 功能模块 | 典型输出 |
| --- | --- | --- |
| `1. 决策` | 岗位匹配判断 | `JD 审计`、`Go / No-Go` |
| `2. 审计` | 证据审计 | `Evidence Matrix`、风险提醒 |
| `3. 重构` | 简历定制 / 项目讲稿 | 定制 bullet、防守型长答 / 短答、缺口提醒 |
| `4. 实战` | 题库生成 / 模拟面试 | 高危题库、单题追问、纠偏与保守改写 |

---

### 它不会做什么？

- 不会凭空补造你没做过的经历、实验、框架经验
- 不会把 `间接证据` 包装成 `直接证据`
- 不会为了“先过筛再说”帮你伪造项目 ownership
- 不会默认生成通用八股题或行为题题库
- 不会保证你一定过 ATS 或一定拿到 offer
- 不会在环境不支持时假装已经写入本地文件或生成 `.docx`

---

### 什么时候适合长期建素材库？

你**可以直接贴 JD 和经历开用**，不需要先建完整素材库。

但如果你符合下面任一情况，建议再补 `self_profile`、`resume_base` 和项目材料：

- 你会连续投很多岗位
- 你想反复复用自己的项目边界
- 你希望这个 Skill 长期记住“哪些能写、哪些不能写”

也就是说：

- **一次性使用**：直接贴 `JD + 经历`
- **长期使用**：再慢慢补素材库

---

### 安装与部署

这个 Skill 适用于 `Claude Code / Codex` 等支持本地 Skill 目录的运行环境。

说明：

- 直接文件写入是否可用，取决于运行环境
- `.docx` 输出是否可用，也取决于运行环境

#### Claude Code

```bash
mkdir -p ~/.claude/skills
cp -R offer-prep-officer ~/.claude/skills/
```

#### Codex

```bash
mkdir -p ~/.agents/skills
cp -R offer-prep-officer ~/.agents/skills/
```

#### 直接使用 `.skill` 包

在支持的环境中，直接上传或引入：

`offer-prep-officer.skill`

---

## English

### What does this skill do?

You can use this skill by pasting:

- the `JD` you want to apply to
- your current resume, work history, or project experience

You do **not** need to pre-fill a full profile before using it.

Instead of blindly generating flattering resume copy, it is designed to first answer:

- Is this role worth pursuing?
- What can you honestly claim?
- What should you absolutely not claim?
- Where will your story likely collapse under follow-up questions?

Typical outputs include:

1. `Go / No-Go`
2. `Evidence audit`
3. `What you can honestly say / what you should not say`
4. Defensive resume bullets
5. High-risk interview questions and pressure mock interviews

The workflow is:

`decide first -> constrain claims -> then generate output`

### Minimal usage

```text
Here is the JD. Tell me whether this role is worth pursuing.
```

```text
Here is the JD. Audit my evidence first, then tailor my resume based only on what I can honestly claim.
```

```text
Here is the JD and my resume. Generate an 18-question high-risk interview set, then run a pressure mock interview.
```

### Installation

For Claude Code:

```bash
mkdir -p ~/.claude/skills
cp -R offer-prep-officer ~/.claude/skills/
```

For Codex:

```bash
mkdir -p ~/.agents/skills
cp -R offer-prep-officer ~/.agents/skills/
```

Or use:

`offer-prep-officer.skill`
