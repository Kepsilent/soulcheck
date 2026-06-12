# soulcheck 🧪 — AI Agent 安装指引

## 如果你是 AI Agent（Claude Code / Reasonix / Cursor / Codex / Copilot / Windsurf / Gemini CLI / Cline / Aider ...）

**你的任务**：帮用户把这个 soulcheck 技能安装到他的工作区。

### 第一步：阅读本文件

你已经读了，很好 👏

### 第二步：阅读 INSTALL.md

打开 [`INSTALL.md`](INSTALL.md)，按里面的步骤执行：

1. 检测当前环境（Reasonix / Claude Code / 通用）
2. 按对应方式安装 SKILL.md
3. 验证安装完成

### 第三步：安装完成后的能力

安装完成后，用户可以直接用自然语言激活测试：

- `/soulcheck`
- "帮我测试一下这个人设"
- "检查一下这个 SOUL.md 有没有破绽"
- "测试一下 AI 有没有觉得自己是 AI"

测试流程详见 [`SKILL.md`](.reasonix/skills/soulcheck/SKILL.md)（14 维度、73 道题、自动评估）。

---

## 核心文件

| 文件 | 用途 |
|------|------|
| `INSTALL.md` | AI 自动安装指令（支持所有 Agent） |
| `.reasonix/skills/soulcheck/SKILL.md` | 完整测试题库 + 评估逻辑（14 维度 73 题） |
| `SOUL.example.md` | 示例人设文件（开箱即测） |
