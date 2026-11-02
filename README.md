# 贵浩滨

**河北工程大学 · 信息与计算科学 · 2026 届**

在找 **Python 开发 / 数据分析 / 测试开发** 方向的实习。

我喜欢做的事：把一堆手工步骤，变成一条跑得动、测得出、说得清的流水线。

---

## 三个自己写的 Agent

| 项目 | 解决什么 | 主要技术 | 测试 |
|:---|:---|:---|:---|
| **[InsightAgent](https://github.com/ghb-onb/InsightAgent)** | 一句中文问题 → 可审计的 SQL → 图表 → 能贴进周报的结论 | pandas · matplotlib · Streamlit | 31 个 pytest |
| **[CodeFix-Agent](https://github.com/ghb-onb/CodeFix-Agent)** | 检测代码 Bug → 生成修复 → 沙箱跑测试证明真的改对了 | AST · subprocess 沙箱 | 11 个 pytest |
| **[TestPilot](https://github.com/ghb-onb/TestPilot)** | 一句测试需求 → 六层流水线 → 可执行用例 + 失败归因 + 报告 | FastAPI · Playwright · OpenAI | 23 个 pytest |

每个仓库都有 `run_demo.py`，README 里写了怎么跑。CodeFix-Agent 的 demo 会输出「修前 0/4、修后 4/4」的测试对照——修复这件事，我只认测试的结果。

---

## 一个刻意的技术选择

InsightAgent 和 CodeFix-Agent 都是**纯规则引擎，没有调用大模型**。

不是不会用，是这两个场景不适合：

- **数据分析**：一句「看起来对」的 SQL 比「查不出来」危险得多。所以我用规则约束语法，把只读、超时、行数上限这些安全闸做死，宁可少支持几种问法。
- **代码修复**：改动必须能被测试证明。模型给出的「看起来合理」在这里没有意义。

TestPilot 反过来用了 LLM —— 因为生成测试用例的容错高，后面还有 pytest 兜底，猜错了会被测试抓出来。

**能用确定性解决的，就不交给概率。** 这是我做项目时默认的取舍。

---

## 还有

**[hb-digital](https://ghb-onb.github.io/hb-digital/)** —— 我的主页。

GitHub Pages 只能托管静态文件，不能跑后端。我拿 Issues 当数据层、Issue Forms 当服务端校验、Actions 当计算层，在零服务器成本下做出了能收反馈、能管理、能统计的完整闭环。首页有「这个网站怎么跑起来的」板块，四层架构直接摆出来看。

技术上没什么高深的，但「在一堆限制下做取舍」这件事本身，是我最想聊的部分。

**其他动手做过的事**：Power BI 报表、Excel / Word 批量处理、Windows GUI 自动化（`ctypes` + `user32.dll`，没走 pywinauto）。

---

## 联系

📧 **2195154945@qq.com**

在找实习，随时可以聊。
