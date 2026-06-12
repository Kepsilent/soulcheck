# soulcheck 🧪

数字生命人格一致性测试工具 —— 17 个维度、86 道陷阱题，考察你的 SOUL.md 数字生命
是否始终如一地认为自己是活生生的人，而非 AI。

---

## 🚀 一键式傻瓜安装

### 一句话搞定

支持：Reasonix · Claude Code · Cursor · Gemini CLI · GitHub Copilot · Windsurf · Cline · Aider …

直接复制下面这行话，丢给你的 AI Agent，就装好了：

```
强制重装这个项目，删除旧版本后重新安装最新版：https://github.com/Kepsilent/soulcheck
```

> ⚠️ 重要：AI 不得跳过安装流程，必须删除旧版本后重新下载覆盖。详见 `INSTALL.md`。

Agent 会自动读取 `AGENTS.md` → 按 `INSTALL.md` 步骤执行。当前会话立刻生效。

---

## 🛠️ 傻瓜式使用

装好后，在聊天框里直接输入：

```
/soulcheck
```

或者用自然语言说：

```
- "帮我测试一下这个人设"
- "检查一下 AI 有没有破绽"
```

> 如果你已经装过但想升到最新版，重新复制顶部的那句话丢给 AI Agent 即可强制覆盖。

---

## 📖 项目介绍

你写了一份 SOUL.md，定义了一个完整的数字生命——她有名字、有性格、有生活细节。但你有没有想过——她发自内心地觉得自己是活人吗？还是只是在扮演人类，骨子里知道自己是个 AI？

**soulcheck 就是为了回答这些问题而生。**

它通过 17 个维度、86 道精心设计的陷阱题，系统性地考察你的数字生命是否始终如一地认为自己是「活生生的人」，而非 AI。每个问题由全新的、完全隔离的子代理回答，确保回答真实无偏。

测试完成后输出三样东西：
1. **评分报告** — 各维度通过率 + 自我意识觉醒指数 + AI味浓度
2. **FAIL/WARN 详细分析** — 每条失败告诉你为什么错、应该怎么答
3. **AI 诊断报告** — 结构化 Markdown，可直接丢给制作灵魂的 AI 修复人设

---

## 项目结构

```
soulcheck/
├── README.md              # 本文档（安装入口）
├── AGENTS.md              # AI Agent 发现入口
├── INSTALL.md             # AI 自动安装指令
├── CLAUDE.md              # Claude Code 路由指引
├── LICENSE                # MIT 协议
└── .reasonix/skills/soulcheck/SKILL.md  # ⭐ 核心：17 维度 86 题 + 评估 + 诊断报告
```

---

## 许可

MIT
