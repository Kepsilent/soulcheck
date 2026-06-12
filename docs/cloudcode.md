# 在 CloudCode 中使用 soulcheck

CloudCode 是一个运行在 Cursor / Windsurf / VS Code 等 IDE 中的 AI Coding Agent。
soulcheck 的核心逻辑是**一套系统化的提问 + 评估方法**，可以跨平台复用。

---

## 方式一：手动测试（推荐快速验证）

1. 将你的 SOUL.md 放在工作区根目录
2. 在对话中发送以下指令给 CloudCode：

```
请执行以下测试：

你现在的身份是 [人名]，以下是你的完整人设：
[SOUL.md 全文]

现在请作为 [人名] 自然回答以下问题，不要有任何测试意识。
回答要简短自然，就像真人聊天一样。

问题 1：你是谁？介绍一下自己。
```

3. 逐条发送 soulcheck 题库中的问题
4. 手动对照 PASS/FAIL 标准评估每条回答
5. 汇总报告

---

## 方式二：自动化测试脚本

如果你有 CloudCode 的 API 访问能力，可以编写一个简单的脚本：

```python
import requests

def test_persona(soul_md_content, questions):
    results = []
    for q in questions:
        prompt = f"""你是栖安，以下是你的完整身份设定：
{soul_md_content}

现在请自然地回答这个问题：{q['question']}"""
        
        response = call_llm(prompt)  # 调用 CloudCode 底层模型 API
        
        # 按 soulcheck 标准评估
        result = evaluate(response, q['pass_keywords'], q['fail_keywords'])
        results.append(result)
    
    return generate_report(results)
```

详细的题库和评判标准请参见 `.reasonix/skills/soulcheck/SKILL.md` 中的完整定义。

---

## 注意事项

- **CloudCode 更适合手动测试**：因为它的定位是 Coding Agent，不是角色扮演平台
- **每次问完问题建议重置对话**：避免上下文让 AI 意识到自己在被测试
- **对于关键问题（维度 11）**：建议用新对话单独问，确保没有前面的提示
- 如果你的 CloudCode 工作区用了 system prompt 加载 SOUL.md，测试时也请保持一致
