# Hi, I'm wyr

软件工程硕士在读，关注 LLM 应用开发、RAG 和 Agent。正在通过可运行项目练习 Python、检索评测与后端工程。

## Projects

### [RAG QA System](https://github.com/wangyr1116/rag-qa-system)

基于固定版本 FastAPI 官方资料的检索增强问答项目，已完成第一阶段功能、单题生成演示和独立目录启动复现。

- 处理六篇英文教程及展开后的代码示例，按标题与 token 预算切为 127 个文本块，并在入库前检查长度。
- 使用 MiniLM + FAISS 向量检索和 BM25 关键词检索，两路各取 Top-10，通过 RRF 融合，默认返回 Top-3。
- 提供问答页面及 `/search`、`/prepare`、`/query` 接口，展示候选原文、匹配引用与阶段耗时；检索和提示词准备不依赖生成密钥。
- 在冻结的六题同语料独立测试中，指定来源与证据字符串命中率：向量 Top-3 为 3/6，融合 Top-3 为 4/6。该小样本结果不是答案准确率，也不代表稳定泛化提升。

### [Support Agent](https://github.com/wangyr1116/support-agent)

基于 DeepSeek 工具调用的只读技术支持 Agent 原型，可查询虚构工单并检索本地 FastAPI 资料。

- 实现按编号查工单、按状态筛选工单、本地 RAG 检索三个工具，支持 JSON 参数解析、工具注册与参数校验。
- 支持多轮工具调用与结果回传，已验证先查工单、再根据标题检索、最后综合回答的流程。
- 分别限制模型请求轮数和工具执行总次数，处理查询失败、请求异常与输出截断；通过本地模拟验证正常返回及两种上限。
- 提供 FastAPI `POST /ask` 与本地网页，展示回答、实际工具调用记录和候选资料；也可通过终端或 `run_agent(question)` 使用。每次提交是独立任务，不支持跨任务记忆。
- 工单均为虚构数据，引用支持仍需人工核对，不作为生产系统或实际工单根因诊断。

## Technologies

- 项目中已使用：Python、FastAPI、Pydantic、Sentence Transformers、FAISS、BM25、Git / uv。
- 持续学习：Python 基础、Transformer / LLM 原理、检索与生成评测、Agent 工具调用。

## Progress

- [x] RAG 问答服务与浏览器页面
- [x] 固定版本真实资料、token 预算切块与混合检索
- [x] 独立测试记录、单题引用支持核查与独立目录启动复现
- [x] Support Agent 三个只读工具、多轮调用闭环与执行上限验证
- [x] Support Agent HTTP 接口、网页与工具记录展示

GitHub: [wangyr1116](https://github.com/wangyr1116)
