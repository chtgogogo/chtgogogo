# 曹灏天（CaoHT）

人工智能专业，本科大四，2027 届。四川内江人，现在找 AI 应用开发 / Vibe Coding / AI 实施交付（FDE）方向的实习，可以长期全职到岗。

我做项目的方式是用 AI Coding Agent。写代码不是我的强项，这点我认。我强的是另外三件事：把一句模糊的需求拆成能落地的东西、判断 AI 给的方案到底对不对、以及东西跑不起来时能定位到是哪一层的问题。下面两个项目都是这么长出来的，从需求、接口设计到评测标准，板是我拍的，代码是 AI 写的。

---

## 项目

### 无畏契约 · 智能问答助手（RAG）

`FastAPI` · `LangChain` · `ChromaDB` · `BM25` · `CrossEncoder` · `GLM-4.7-Flash` · `SSE`

游戏攻略散在几十个网页和视频里，版本还老，查一个问题要翻半天。这个项目把它们收进一个能版本管理的知识库，AI 回答之前先检索，每条结论都指得出出处——答不了就明说，绝不瞎编。

- 检索分三级。查询改写负责处理多轮对话里的指代，混合检索把 BM25 和向量结果用 RRF 融合，最后过一遍 CrossEncoder 重排序。无关问题拒答正确率 0% → 100%
- 评测体系驱动迭代：6 套评测集按 7:3 冻结切成训练集和盲测集，对外只报盲测数字（holdout 14 题，Hit@5 75.0%、MRR 0.61，2026-09-25 实测）。消融发现混合检索在当前库规模零收益、查询改写净收益存疑——都照实写在 README 里
- 成本与体验治理：免费档晚高峰未命中 70.7s → 切付费通道 5.7s → 语义缓存命中约 10ms；另做了 IP 双层限流、输入限长和提示词注入三层防护

👉 在线演示：[rag.caohaotian.top](https://rag.caohaotian.top/) ｜ [valorant-rag-assistant](https://github.com/chtgogogo/valorant-rag-assistant)

### 校园失物招领 · 智能匹配系统

`FastAPI` · `Vue3` · `YOLOv8` · `CLIP` · `七维加权匹配` · `Docker`

丢东西的人和捡到东西的人，以前只能靠人工翻帖子一张张比对。这个系统让机器先看懂物品长什么样，再用一套能解释的规则把两边撮合起来，交接用双码验证防冒领。

- 匹配引擎有七个维度：类目、颜色、数量、地点、状态、关键词、时间衰减，权重合计 100 分，加一层动态归一化处理信息填不全的情况。自建 40 对人工标注评测集，匹配 F1 从 62.9% 做到 78.0%、召回从 55% 做到 80%，CI 设了 F1 低于 76 就阻断合并
- 图像走双通道，YOLOv8 做物品分类，感知哈希和 CLIP 做相似度。没有 GPU 也能降级运行。识别链路异步化后压测 QPS 从 5.4 到 74.4、p95 从 1800ms 到 68ms
- 交接环节用双码交叉验证防冒领（10 秒时效验证码 + 恒时比较 + 连错锁定 + 数据库行锁）。449 个自动化测试全绿，还有一套 12 对冻结盲测集防"用考卷练题"

👉 在线演示：[lost.caohaotian.top](https://lost.caohaotian.top/) ｜ [campus-lost-found-system](https://github.com/chtgogogo/campus-lost-found-system)

### AI Agent 技能工具箱

在真实项目里磨出来的一套 AI Skill，管技能调度、编码规范、记忆纪律、多 Agent 协作和踩坑沉淀。不绑定任何 Agent 框架，只描述规则、流程和边界。配套体检器和调用统计：规则要改必须跑通检查才允许入库，用每日巡检防止规则腐烂。

👉 [Caoht-skills](https://github.com/chtgogogo/Caoht-skills)

---

## 技术栈

- **AI 应用**：RAG 全链路（文档切分、Embedding、混合检索、重排序、评测集搭建）、Agent 工作流、Tool Calling、Prompt 工程
- **后端**：Python、FastAPI、SQLAlchemy、RESTful API、JWT
- **前端**：Vue3 + Element Plus。AI 生成的页面代码我能读懂、能改，也能和后端联调
- **工具**：Git / GitHub、Docker 基础、智谱与 OpenAI 兼容 API

---

## 做事方式

需求有歧义我会停下来问清楚，不猜。两个项目的接口和数据结构都是我定的，AI 负责实现，每一层为什么这么选我能讲出来。

我也不太靠感觉调参。两个项目都建了评测集，F1 和 Hit@5 怎么动、改动前后差多少，都记在数据里。检索数字随知识库版本变化，所以我给每个数字都标评测日期，改动必重跑。

时间上没什么牵绊。大四已经没有课业安排，实习可以长期全职。

---

## 联系

📧 1207912646@qq.com ｜ 🐙 [@chtgogogo](https://github.com/chtgogogo) ｜ 🌐 [my.caohaotian.top](https://my.caohaotian.top/)

---

![chtgogogo's GitHub stats](https://github-readme-stats.vercel.app/api?username=chtgogogo&show_icons=true&theme=tokyonight)
