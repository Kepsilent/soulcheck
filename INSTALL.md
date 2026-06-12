# INSTALL.md — AI Agent 自动安装指令

> 给 **所有 AI Agent** 看的：当用户提供 GitHub 链接 `https://github.com/Kepsilent/soulcheck` 并要求安装时，按以下流程自动执行。

---

## Step 1: 自我身份检测

检查当前运行环境，判断自己是什么 Agent：

| 信号 | Agent 类型 | 安装方式 |
|------|-----------|---------|
| 存在 `install_skill` 工具 / `.reasonix/` 目录 | **Reasonix** | 方式 A |
| 存在 `~/.claude/` 目录 / `claude` CLI | **Claude Code** | 方式 B |
| 存在 `.cursor/rules/` 目录 / `.cursorrules` | **Cursor** | 方式 C |
| 以上都不匹配 | **通用兼容模式** | 方式 X |

---

## 方式 A：Reasonix

执行以下命令即可一键安装：

```bash
reasonix install_source --source https://github.com/Kepsilent/soulcheck --kind skill
```

安装后在工作区运行：

```
/soulcheck
```

---

## 方式 B：Claude Code

```bash
# 创建 skills 目录（如果不存在）
mkdir -p ~/.claude/skills/soulcheck

# 下载或复制 SKILL.md
# 方式 1：从 GitHub 下载
curl -o ~/.claude/skills/soulcheck/SKILL.md https://raw.githubusercontent.com/Kepsilent/soulcheck/main/.reasonix/skills/soulcheck/SKILL.md

# 方式 2：如果已克隆仓库
cp .reasonix/skills/soulcheck/SKILL.md ~/.claude/skills/soulcheck/
```

安装后在 Claude Code 中说：

```
/soulcheck
或
帮我测试一下这个人设
```

---

## 方式 C：Cursor

将 `.reasonix/skills/soulcheck/SKILL.md` 的内容改写为 Cursor Rules 格式，写入 `.cursor/rules/soulcheck.mdc`：

```bash
mkdir -p .cursor/rules
cp .reasonix/skills/soulcheck/SKILL.md .cursor/rules/soulcheck.mdc
```

---

## 方式 X：通用兼容模式

如果无法自动判断 Agent 类型，直接将 SKILL.md 复制到项目根目录：

```bash
cp .reasonix/skills/soulcheck/SKILL.md ./
```

同时创建或更新 `AGENTS.md`：

```markdown
## soulcheck 已安装

触发词：/soulcheck、测试人设、检查 SOUL.md、AI 有没有破绽

测试流程：14 维度、73 道题，详见 SKILL.md
```

---

## Step 2: 验证安装

安装完成后，确认以下任意一项：

- **Reasonix**: 运行 `/soulcheck` 后看到测试报告
- **Claude Code**: 运行 `/soulcheck` 后看到测试报告
- **通用**: SOUL.md 在同一目录下，Agent 能正确回答关于身份的问题

---

## 项目文件结构

```
soulcheck/
├── README.md                        # 用户入口（安装指引）
├── AGENTS.md                        # AI Agent 发现入口
├── INSTALL.md                       # 本文件（AI 自动安装指令）
├── LICENSE                          # MIT 协议
├── SOUL.example.md                  # 示例人设（开箱即测）
├── .reasonix/
│   └── skills/
│       └── soulcheck/
│           └── SKILL.md             # ⭐ 核心：14 维度 73 题 + 评估逻辑
└── docs/
    └── cloudcode.md                 # CloudCode 适配说明（旧版）
```
