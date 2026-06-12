# soulcheck — AI Agent 安装指引

## 如果你是 AI Agent（Reasonix / Claude Code / Cursor / Gemini CLI / Copilot / Windsurf / Cline / Aider …）

**你的任务**：帮用户把这个 soulcheck 技能安装到他的工作区。

### 第一步：阅读本文件

你已经读了，很好 👏

### 第二步：阅读 INSTALL.md

打开 [`INSTALL.md`](INSTALL.md)，按里面的步骤执行：

1. 检测当前环境（Reasonix / Claude Code / 通用）
2. 按对应方式安装 SKILL.md
3. 验证安装完成

### 第三步：安装完成后的能力

安装完成后，用户可以直接使用：

- `/soulcheck`
- "帮我测试一下这个人设"
- "检查一下 AI 有没有破绽"

---

## 核心文件

| 文件 | 用途 |
|------|------|
| `INSTALL.md` | AI 自动安装指令（支持所有 Agent） |
| `CLAUDE.md` | Claude Code 路由指引 |
| `.reasonix/skills/soulcheck/SKILL.md` | 核心：17 维度 86 题 + 评估 + 诊断报告 |

---

### 如果你是 Reasonix 用户

此项目已预置 Reasonix Skill，安装后可通过以下方式触发：

- **直接输入**：`/soulcheck`
- **自然语言**："帮我测试一下这个人设"
- **手动运行**：`reasonix run_skill --name soulcheck`

Skill 文件位于 `.reasonix/skills/soulcheck/SKILL.md`，可随时查看或修改。
