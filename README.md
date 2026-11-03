# 贵浩滨

**河北工程大学 · 信息与计算科学 · 2026 届**

在找 **Python 开发 / 数据分析 / 测试开发** 方向的实习。

我喜欢做的事：把一堆手工步骤，变成一条跑得动、测得出、说得清的流水线。

---

## 三个自己写的 Agent

| 项目 | 解决什么 | 主要技术 | 测试 |
|:---|:---|:---|:---|
| **[InsightAgent](https://github.com/ghb-onb/InsightAgent)** | 一句中文问题 → 可审计的 SQL → 图表 → 能贴进周报的结论 | pandas · matplotlib · Streamlit | 44 个 pytest |
| **[CodeFix-Agent](https://github.com/ghb-onb/CodeFix-Agent)** | 检测代码 Bug → 生成修复 → 沙箱跑测试证明真的改对了 | AST · subprocess 沙箱 | 11 个 pytest |
| **[TestPilot](https://github.com/ghb-onb/TestPilot)** | 一句测试需求 → 六层流水线 → 可执行用例 + 失败归因 + 报告 | FastAPI · Pydantic · SQLite | 23 个 pytest |

每个仓库都有 `run_demo.py`，README 里写了怎么跑。CodeFix-Agent 的 demo 会输出「修前 0/4、修后 4/4」的测试对照——修复这件事，我只认测试的结果。

---

## 一个刻意的技术选择

InsightAgent 和 CodeFix-Agent 都是**纯规则引擎，没有调用大模型**。

不是不会用，是这两个场景不适合：

- **数据分析**：一句「看起来对」的 SQL 比「查不出来」危险得多。所以我用规则约束语法，把只读、超时、行数上限这些安全闸做死，宁可少支持几种问法。
- **代码修复**：改动必须能被测试证明。模型给出的「看起来合理」在这里没有意义。

TestPilot 目前也是纯规则 + Mock 执行——**LLM 和真实浏览器都还在 Roadmap 里，没装成已完成**。执行层就是 `MockExecutor`（真实浏览器的 `PlaywrightExecutor` 还没写），规划层有 `use_llm` 参数但默认关着、也没接任何模型。这不是将就：5 类场景用关键词映射命中率就是 100%，一次解析不到 1ms、零费用、结果可复现。等它长到 50 类场景、长尾表述多起来，再谈接模型。

**能用确定性解决的，就不交给概率。** 这是我做项目时默认的取舍。

---

## 还有

**[hb-digital](https://ghb-onb.github.io/hb-digital/)** —— 我的主页，也是我的技术作品集。

GitHub Pages 只能托管静态文件，不能跑后端。我拿 Issues 当数据层、Issue Forms 当服务端校验、Actions 当计算层，在零服务器成本下做出了能收反馈、能管理、能统计的完整闭环。架构取舍写在仓库的 README 里，网站本身只负责讲清楚「我是谁、会什么、做过什么」。

技术上没什么高深的，但「在一堆限制下做取舍」这件事本身，是我最想聊的部分。

**GTIT 企业官网** —— [gtit.cc](https://gtit.cc) · [my-website](https://github.com/ghb-onb/my-website)

企业项目，不是个人作品。宁波一家齿轮减速机出口企业的英文站，站点共 14 个内容页面（9 个主页面 + 5 篇技术博客），线上在运营。

我负责的是内容与模块增量：在既有模板上新增博客模块——列表页重排、5 篇技术文章详情页、导航与文章互链，沿用站点原有的 Bootstrap + GSAP 动效体系，不引入新框架。改的是内容和结构，不是从零搭站——企业站的约束比个人项目多，动一个列表项都得先对一遍现有样式规范。

**其他动手做过的事**：Power BI 报表、Excel / Word 批量处理、Windows GUI 自动化（`ctypes` + `user32.dll`，没走 pywinauto）。

---

## 联系

📧 **2195154945@qq.com**

在找实习，随时可以聊。
