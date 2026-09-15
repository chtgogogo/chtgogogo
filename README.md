# 曹灏天（CaoHT）

人工智能专业，本科大三，2027 届。四川内江人，现在找 AI 应用开发方向的实习，可以长期全职到岗。

我做项目的方式是用 AI Coding Agent。写代码不是我的强项，这点我认。我强的是另外三件事：把一句模糊的需求拆成能落地的东西、判断 AI 给的方案到底对不对、以及东西跑不起来时能定位到是哪一层的问题。下面两个项目都是这么长出来的，从需求、接口设计到评测标准，板是我拍的，代码是 AI 写的。

---

## 项目

### 校园失物招领 · 智能匹配系统

`FastAPI` · `Vue3` · `YOLOv8` · `CLIP` · `七维加权匹配` · `Docker`

丢东西的人和捡到东西的人，以前只能靠人工翻帖子一张张比对。这个系统让机器先看懂物品长什么样，再用一套能解释的规则把两边撮合起来。

- 匹配引擎有七个维度：类目、颜色、数量、地点、状态、关键词、时间衰减，权重合计 100 分，加一层动态归一化处理信息填不全的情况
- 图像走双通道，YOLOv8 做物品分类，感知哈希和 CLIP 做相似度。没有 GPU 也能降级运行
- 我自建了 40 对人工标注评测集（正负例各 20），拿它调参数，匹配 F1 从 58.8% 提到 62.9%
- 交接环节用双码交叉验证防冒领，配合 API 限流和图片魔数校验。目前 389 个自动化测试全绿

👉 [campus-lost-found-system](https://github.com/chtgogogo/campus-lost-found-system)

### 无畏契约 · 智能问答助手（RAG）

`FastAPI` · `LangChain` · `ChromaDB` · `BM25` · `CrossEncoder` · `GLM-4-Flash` · `SSE`

游戏攻略散在几十个网页和视频里，版本还老，查一个问题要翻半天。这个项目把它们收进一个能版本管理的知识库，AI 回答之前先检索，每条结论都指得出出处。

- 检索分三级。查询改写负责处理多轮对话里的指代，混合检索把 BM25 和向量结果用 RRF 融合，最后过一遍 CrossEncoder 重排序
- 20 题评测集驱动迭代。无关问题的拦截率从 0% 做到 100%，检索 Hit@5 是 94.1%
- 升级后 MRR 从 0.882 掉到 0.796，原因是 BM25 把弱关联的文档块带进了候选，入门级重排模型纠不回来。这条我照实写在 README 里
- 领域内容全部配置化，换一份配置就能改成企业知识库助手，代码一行不动

👉 [valorant-rag-assistant](https://github.com/chtgogogo/valorant-rag-assistant)

### AI Agent 技能工具箱

在真实项目里磨出来的一套 AI Skill，管技能调度、编码规范、记忆纪律、多 Agent 协作和踩坑沉淀。不绑定任何 Agent 框架，只描述规则、流程和边界。

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

我也不太靠感觉调参。两个项目都建了评测集，F1 和 Hit@5 怎么动、改动前后差多少，都记在数据里。上面那条 MRR 下降的记录也在。

时间上没什么牵绊。大三已经没有课业安排，实习可以长期全职。

---

## 联系

📧 1207912646@qq.com ｜ 🐙 [@chtgogogo](https://github.com/chtgogogo)

---

![chtgogogo's GitHub stats](https://github-readme-stats.vercel.app/api?username=chtgogogo&show_icons=true&theme=tokyonight)
