# Hi, I'm wyr

软件工程硕士在读，关注 LLM 应用开发、RAG 和 Agent。正在通过可运行项目练习 Python、检索评测与后端工程。

## Projects

### [RAG QA System](https://github.com/wangyr1116/rag-qa-system)

基于固定版本 FastAPI 官方资料的检索增强问答项目，已完成第一阶段功能、单题生成演示和独立目录启动复现。

- 处理六篇英文教程及展开后的代码示例，按标题与 token 预算切为 127 个文本块，并在入库前检查长度。
- 使用 MiniLM + FAISS 向量检索和 BM25 关键词检索，两路各取 Top-10，通过 RRF 融合，默认返回 Top-3。
- 提供问答页面及 `/search`、`/prepare`、`/query` 接口，展示候选原文、匹配引用与阶段耗时；检索和提示词准备不依赖生成密钥。
- 在冻结的六题同语料独立测试中，指定来源与证据字符串命中率：向量 Top-3 为 3/6，融合 Top-3 为 4/6。该小样本结果不是答案准确率，也不代表稳定泛化提升。

### Support Agent（规划中）

计划实现技术支持助手：调用资料检索和模拟工单查询两个只读工具，练习工具选择、参数校验、结果回传、最大步骤与失败出口。目前仅完成方向设计，尚未实现 Agent 执行链路。

## Technologies

- 项目中已使用：Python、FastAPI、Pydantic、Sentence Transformers、FAISS、BM25、Git / uv。
- 持续学习：Python 基础、Transformer / LLM 原理、检索与生成评测、Agent 工具调用。

## Progress

- [x] RAG 问答服务与浏览器页面
- [x] 固定版本真实资料、token 预算切块与混合检索
- [x] 独立测试记录、单题引用支持核查与独立目录启动复现
- [ ] Support Agent 工具调用闭环

GitHub: [wangyr1116](https://github.com/wangyr1116)
