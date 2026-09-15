# 👋 我是 曹灏天（CaoHT）

> 用 AI Coding Agent 把想法变成能跑的产品。我不拼手写代码，拼「看懂架构 → 给 AI 下精准指令 → 验收结果 → 讲清设计」。

🎓 人工智能专业 · 本科大三（2027 届） ｜ 📍 四川 ｜ 💼 **正在找 AI 应用开发实习，可长期全职**

---

## 🚀 我的项目

### 🔍 校园失物招领 · 智能匹配系统
**FastAPI · Vue3 · YOLOv8 · CLIP · 七维加权匹配 · Docker**

> 让「丢东西的人」和「捡到东西的人」不再靠人工翻帖子。

- 设计**七维加权打分引擎** + 动态归一化；自建 40 对人工标注评测集，匹配 F1 从 58.8% 提升至 **62.9%**
- YOLOv8 物品识别 + 感知哈希/CLIP 图像相似度**双通道**，**全部支持无 GPU 降级运行**
- **双码交叉验证**防冒领；**389 个自动化测试**全绿的质量基线

👉 **[点这里看代码 → campus-lost-found-system](https://github.com/chtgogogo/campus-lost-found-system)**

### 🎮 无畏契约 · 智能问答助手（RAG）
**FastAPI · LangChain · ChromaDB · BM25 · CrossEncoder · GLM-4-Flash · SSE**

> 把散落各处的游戏知识收进可维护的知识库，让 AI 边检索边回答，每条结论都指得出出处。

- 检索**三级管线**：查询改写（多轮指代消解）→ 混合检索（BM25 + 向量，RRF 融合）→ CrossEncoder 重排序
- **自建 20 题评测集**数据驱动迭代：无关问题拦截率 **0% → 100%**，检索 Hit@5 **94.1%**
- **领域配置化**：换一份配置即可迁移为企业知识库助手，代码零修改

👉 **[点这里看代码 → valorant-rag-assistant](https://github.com/chtgogogo/valorant-rag-assistant)**

### 🧰 AI Agent 技能工具箱
> 在真实项目中打磨、可跨多种 Agent 框架复用的 AI Skill 集合——技能调度 / 编码铁律 / 记忆纪律 / 多 Agent 协作治理 / 踩坑沉淀。

👉 **[点这里看全部 Skill → Caoht-skills](https://github.com/chtgogogo/Caoht-skills)**

---

## 🛠 技术栈

- **AI 应用**：RAG 全链路（切分 / Embedding / 混合检索 / 重排序 / 评测）、Agent 工作流、Tool Calling、Prompt 工程
- **后端**：Python · FastAPI · SQLAlchemy · RESTful API · JWT
- **前端**：Vue3 + Element Plus（能读懂 AI 生成的代码并完成调整与联调）
- **工具**：Git/GitHub · Docker 基础 · 智谱 / OpenAI 兼容 API

---

## 💼 我能带来什么

- **AI 方向舵**：主导需求拆解与设计决策，AI 辅助实现，能讲清每一层的取舍
- **数据驱动**：习惯用评测集 + 指标（F1 / Hit@5）驱动迭代，而不是"凭感觉调参"
- **即时到岗**：大三已无课业安排，可长期全职实习

---

## 📫 联系方式

- 📧 1207912646@qq.com
- 🐙 GitHub：[@chtgogogo](https://github.com/chtgogogo)

---

![chtgogogo's GitHub stats](https://github-readme-stats.vercel.app/api?username=chtgogogo&show_icons=true&theme=tokyonight)
