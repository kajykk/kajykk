<h1 align="center">kajykk</h1>

<p align="center">
  <b>后端 / AI 工程</b> · Python · FastAPI · 多模态 ML 与 MLOps · 全栈（Vue 3 + TypeScript）
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/FastAPI-async-009688?logo=fastapi&logoColor=white" alt="FastAPI">
  <img src="https://img.shields.io/badge/Vue_3-TypeScript-42b883?logo=vuedotjs&logoColor=white" alt="Vue 3">
  <img src="https://img.shields.io/badge/ML-LightGBM_·_XGBoost_·_BERT-ff69b4" alt="ML">
  <img src="https://img.shields.io/badge/LLM-RAG_·_Agent-8A2BE2" alt="LLM">
  <img src="https://img.shields.io/badge/Ops-Docker_·_Prometheus_·_Grafana-2496ED" alt="Ops">
</p>

---

## 我在做什么

我不满足于「把模型跑通」——**更关心模型上线之后的事**：怎么尽早发现它退化了、怎么安全地放量、怎么解释它的每一次判断、怎么在合规前提下处理用户数据。

下面 5 个项目横跨 **心理健康 · 人力资源 · 金融风控 · 企业知识管理** 四个场景，但共用同一条工程基线：

```
多模态融合  →  可解释  →  漂移监控  →  金丝雀发布  →  全链路可观测  →  隐私合规
```

---

## 精选项目

| 项目 | 场景 | 技术要点 | 关键指标 |
| :-- | :-- | :-- | :-- |
| **[bysj](https://github.com/kajykk/bysj)**<br>心理健康风险评估系统（DWS） | 高校心理筛查与预警 | 多模态融合（问卷 + 文本 BERT + 生理信号）· WebSocket 实时告警 · Celery 异步链路 · PII 加密 | Prometheus + Grafana + Sentry + OpenTelemetry 全链路可观测 |
| **[hr-attrition](https://github.com/kajykk/hr-attrition)**<br>企业员工离职风险预警（HRA） | 人力资源 | LightGBM + IsolationForest 融合评分 · SHAP 个体归因 · 特征契约校验（推理 / 训练一致性） | 测试 AUC **0.9862**<br>Top-20% 离职召回 **0.8832** |
| **[fraud-risk-detection](https://github.com/kajykk/fraud-risk-detection)**<br>实时金融反欺诈（FRD） | 金融风控 | 规则引擎 + XGBoost / BERT 多模态 · GraphSAGE + Louvain 团伙检测 | 漂移检测 · Kill Switch · 金丝雀发布 · 对标 PCI-DSS / PIPL |
| **[nexusrag](https://github.com/kajykk/nexusrag)**<br>企业级 RAG 知识库 | 企业知识管理 | 向量 + BM25 + RRF 三阶混合检索 · 引用溯源到页码 · Plan-Reflect-Synthesize Agent · SSE 流式 | Vue 3 + Express + TypeScript 全栈<br>内置 Demo 模式（无 Key 可体验） |
| **[library](https://github.com/kajykk/library)**<br>自托管电子书与知识库 | 个人知识管理 | Next.js 14 + FastAPI · SQLite FTS5 中文 trigram 检索 · Yjs CRDT 实时协作 · 双向链接知识图谱 | 25 个 pytest + Playwright e2e<br>Docker Compose 一键启动 |

---

## 一套贯穿所有项目的工程基线

- **可解释优先** — SHAP 个体归因 + 特征契约校验，确保「推理用它训练时用过的特征」，而不是黑盒出数
- **上线可控** — 金丝雀发布、影子模式、Kill Switch、一键回滚，把「放量」当成有预案的操作
- **不信任静态指标** — 漂移检测 + 公平性审计，把「模型退化」当作一等公民处理，而不是等业务报警
- **合规内建** — PII 加密、审计日志、数据导出与删除，对齐 PIPL / PCI-DSS
- **可观测性** — Prometheus 指标 + Grafana 看板 + Sentry 异常 + OpenTelemetry 链路追踪
- **测试兜底** — 每个项目都有 pytest 单元测试、前端静态类型检查、e2e 冒烟与 GitHub Actions CI

---

## 技术栈

| 层 | 技术 |
| :-- | :-- |
| **后端** | Python 3.12 · FastAPI · SQLAlchemy 2 · Alembic · Celery · Redis · PostgreSQL / SQLite |
| **ML / LLM** | LightGBM · XGBoost · scikit-learn · BERT · GraphSAGE · SHAP · RAG（向量 + BM25 + RRF）· Agent 工作流 |
| **前端** | Vue 3 · TypeScript · Vite · Pinia · Element Plus · Next.js 14 · Tailwind CSS |
| **工程 / 运维** | Docker & Compose · GitHub Actions · Prometheus · Grafana · Sentry · OpenTelemetry · pytest & Playwright |

---

## 怎么看这些项目

- 每个仓库的 README 都写了**技术栈、架构、快速开始与成果数据**，`docs/` 下有架构文档与运维手册
- 多数项目支持 `docker compose up` 或一条命令本地启动，可直接跑起来看效果
- 代码按生产标准组织：含数据库迁移脚本、CI 流水线、测试套件与部署文档

<sub>以上均为个人作品。项目里的性能数字取自各仓库 README 记录的测试结果。</sub>
