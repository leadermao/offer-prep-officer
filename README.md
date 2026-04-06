# 🎯 Job Hunt Copilot — Claude Skill

> 你的专属求职助手。把简历修改、项目叙事重构、面试讲稿生成、模拟面试全部交给 Claude 来做。

[English](#english) | [中文](#中文)

---

## 中文

### 这个 Skill 解决什么问题？

求职是一件**高度重复但又高度定制化**的事情：

- 每投一个岗位，简历就要改一遍——措辞、项目顺序、侧重点全都不同
- 同一个项目，投产品岗和投运营岗，讲法完全不一样
- 面试前要准备口述讲稿，既要精炼，又要和 JD 对上
- 模拟面试没人陪练，只能自己对着镜子说

这个 Skill 的核心思路是：**把你的项目历程一次性存入「素材库」，之后每次投岗位，Claude 直接从素材库取材，按岗位定制输出。**

---

### 能做什么？

| 功能 | 触发方式 | 输出 |
|------|---------|------|
| **简历定制** | 「帮我针对这个 JD 改简历」 | 定制版 `.docx` 简历，附修改说明 |
| **项目叙事重构** | 「帮我从产品角度重构这个项目」 | 简历 bullet 版 + 面试口述版（STAR 结构） |
| **项目讲稿生成** | 「帮我生成项目讲稿」 | 双语 `.docx` 讲稿，每项目含中英文各一页 + 可能追问 |
| **项目文件录入** | 「我有个新项目，帮我录入」 | 结构化项目文件，存入素材库 |
| **模拟面试** | 「帮我模拟面试」 | 交互式面试，可选友好复盘 / 高压追问模式 |

---

### 安装方法

1. 下载 `job-hunt-copilot.skill` 文件
2. 打开 [Claude.ai](https://claude.ai) → Settings → Skills
3. 点击「Install Skill」，上传 `.skill` 文件
4. 安装完成，在任意对话中说出触发词即可启动

---

### 快速上手（推荐顺序）

#### 第一步：填写个人档案

打开安装好的 Skill，对 Claude 说：

```
帮我填写 self_profile，我叫XX，目前在XX，目标岗位是XX产品经理...
```

Claude 会引导你补全背景、技能、求职偏好。

#### 第二步：录入简历母版

把你现有的简历发给 Claude：

```
这是我的简历，帮我更新 resume_base.md
```

#### 第三步：录入项目

把项目相关的文档、说明、聊天记录发给 Claude：

```
我有一个新项目要录入，这是项目说明：[粘贴内容]
```

Claude 会按结构化模板提炼并保存。**项目越详细，后续输出质量越高。**

#### 第四步：开始投岗位

素材库建好后，直接用：

```
我要投这个岗位，帮我改简历 + 生成项目讲稿：[粘贴 JD]
```

---

### 输出示例

**简历定制**：Claude 会告诉你选了哪些项目、排除了哪些、为什么，然后输出 `.docx` 文件。

**项目讲稿**：每个项目生成双语讲稿（中文 + English），结构固定：
```
开场句 → 背景与问题 → 我做了什么 → 结果 → 与本岗位的连接
```
结尾附 2-3 条「可能追问」，让你提前准备。

**模拟面试**：开始前选择风格（友好复盘 / 高压追问）和类型（BQ / JD 面 / 混合），结束后给出复盘报告。

---

### 素材库结构

```
job-hunt-copilot/
├── SKILL.md                    # 主指令（无需修改）
└── resources/
    ├── self_profile.md         # 你的背景、技能、求职偏好
    ├── resume_base.md          # 全量简历母版
    ├── project_template.md     # 项目文件模板
    └── projects/
        ├── 项目A.md            # 每个项目一个文件
        └── 项目B.md
```

**更新素材库**：直接告诉 Claude 需要修改的内容，它会帮你写回文件。或者把 `.skill` 文件改后缀为 `.zip` 解压，手动编辑后重新打包安装。

---

### 适合谁用？

- 正在求职、需要频繁修改简历的应届生或职场人
- 有多个项目经历、需要针对不同岗位重新组织叙事的候选人
- 投递国际岗位、需要中英双语简历和讲稿的求职者
- 没有人陪练面试、需要一个随时可用的模拟面试搭档的人

---

### 注意事项

- Skill 需要 Claude Pro / Team 账号才能使用
- 素材库越完整，输出质量越好——建议至少录入 2-3 个项目后再开始投简历
- Claude 不会凭空编造项目细节，所有叙事都基于你录入的真实内容

---

---

## English

### What problem does this Skill solve?

Job hunting is **highly repetitive but uniquely customized** every time:

- Every application requires a tweaked resume — different wording, project order, and emphasis
- The same project needs to be framed completely differently for a PM role vs. an ops role
- Interview pitch scripts take time to prepare, and they need to align precisely with the JD
- Mock interviews are hard to practice without a partner

The core idea: **Store your project history once in a "material library." Every time you apply, Claude pulls from that library and produces tailored outputs for that specific role.**

---

### What can it do?

| Feature | How to trigger | Output |
|---------|---------------|--------|
| **Resume Tailoring** | "Help me tailor my resume for this JD" | Customized `.docx` resume with change notes |
| **Narrative Reframing** | "Reframe this project from a product angle" | Resume bullets + interview pitch (STAR format) |
| **Pitch Script Generation** | "Generate pitch scripts for this JD" | Bilingual `.docx` — one CN page + one EN page per project, with likely follow-up questions |
| **Project Intake** | "I have a new project to add" | Structured project file saved to library |
| **Mock Interview** | "Let's do a mock interview" | Interactive interview, choice of friendly debrief or high-pressure mode |

---

### Installation

1. Download `job-hunt-copilot.skill`
2. Go to [Claude.ai](https://claude.ai) → Settings → Skills
3. Click "Install Skill" and upload the `.skill` file
4. Done — use any trigger phrase in any conversation to activate

---

### Quick Start (recommended order)

**Step 1 — Fill in your profile**
```
Help me fill in self_profile. My name is X, currently in X, targeting X PM roles...
```

**Step 2 — Add your base resume**
```
Here's my resume. Please update resume_base.md.
```

**Step 3 — Add your projects**
```
I have a new project to add. Here's the description: [paste content]
```
The more detail you provide, the better the outputs.

**Step 4 — Start applying**
```
I want to apply for this role. Help me tailor my resume and generate pitch scripts: [paste JD]
```

---

### Pitch Script Format

Every project gets two pages — Chinese and English — each structured as:

```
Opening line → Background & Problem → What I Did → Result → Connection to This Role
```

Followed by 2-3 likely follow-up questions to help you prepare.

---

### Who is this for?

- Job seekers who need to frequently customize resumes for different roles
- Candidates with multiple projects who need different narratives for different positions
- International applicants who need bilingual (CN/EN) resumes and pitch scripts
- Anyone who wants an always-available mock interview partner

---

### Tips

- Requires Claude Pro or Team account
- The richer your project library, the better the outputs — aim for at least 2-3 projects before applying
- Claude only draws from your real project content — it will never fabricate details

---

### License

MIT — feel free to fork, modify, and share.

---

*Built with Claude Skill system. Contributions and issues welcome.*
