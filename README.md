# Hi, I'm Cian Lien 👋

**AI 全栈工程师** ｜ Go 后端 + React 前端 ｜ 广州 / 深圳 ｜ 一周内到岗

前端出身，现在独立负责 Go 后端和 AI Agent 链路。从 Agent 工具调用、结构化校验、消息队列，到 React 运营后台和线上监控，一个人能把一条 AI 功能从后端到前端交付上线。

- 🤖 **AI 应用**：Eino、LangChain、LangGraph、Langfuse｜Tool Calling、结构化输出、RAG、MCP、Prompt 工程、模型成本优化
- ⚙️ **后端**：Go、Gin、gRPC、GORM｜Kafka、RabbitMQ、Redis、PostgreSQL / MySQL
- ☁️ **云原生**：Docker、Kubernetes、Helm、Nacos｜Prometheus、Grafana、Sentry
- 🖥 **前端**：React 19、Next.js、TypeScript、TanStack Query、Zustand、Tailwind CSS、Flutter
- 📫 **联系我**：cianlien06@gmail.com

---

## 🚀 做过的项目

### AI 热点分析与智能运营平台 · 全栈（独立负责）

聚合实时行情、社交媒体和外部公开信息，由 Agent 完成内容理解、指标分析、AI 评分和报告生成，运营人员在后台管理整个流程。

**后端与 AI**
- 基于 **Eino** 编排多步分析。行情查询、指标计算和历史评分检索都封装成 Tools，由模型按步骤自己选择调用
- AI 评分用 **JSON Schema** 约束输出，服务端校验字段和取值范围，不合规的结果自动重试或降级，保证评分能入库、能对比
- 任务状态机覆盖创建、执行、失败重试、人工重跑和结果发布；Kafka 处理数据消费，RabbitMQ 处理任务投递和延迟重试
- 用模板路由和 Prompt 缓存，**月度模型费用从 1.2 万元降到 7,400 元（约降 38%）**

**前端**
- 基于 **React 19 + TypeScript + TanStack Router / Query** 实现运营后台：任务管理、历史记录、AI 评分、Prompt 与模型配置、结果发布、权限管理
- 支持模板热更新，以及评分规则和告警策略的在线配置，运营调整 Prompt 不需要发版

**可观测性**
- 用 Langfuse 记录每次分析的耗时、Token、异常和结果，用来评估效果和追踪成本

### 多源数字资产行情平台 · 后端负责人

这个项目体现后端深度：4 个 Go 微服务（订阅、采集、行情处理、API），部署在阿里云 ACK 上。

- 行情处理服务 6 副本，每分钟处理约 **6.6 万条**行情
- raw → normalized → effective 三段链路做多源择优和乱序防护，来源下线时用 CAS 原子清理
- 订阅统一建模为“订阅租约”，通过 Outbox 可靠下发；冷启动的 8,700 个订阅合批下发，避开上游限流
- 用 pprof 定位 JSON 重复解码热点，**总 CPU 下降 21.8%**；搜索延迟从 **2.5s 降到约 0.3s**

### 工程化

- 资产列表接口 P99 从 **680ms 降到 120ms**（PostgreSQL 表结构 + Redis 热点缓存）
- 用 Docker 自建 Sentry，覆盖 5+ 个项目，接入 SourceMap 和飞书告警，故障发现缩短到分钟级
- 搭建覆盖 Web、Android、iOS 的多环境 CI/CD，发版人工步骤从 **12 步减到 3 步**
- 前端完成行情图表、交易流程、资产管理和 AI 对话等核心模块，沉淀了项目脚手架和通用请求层

> 以上是公司项目，代码没有公开。

---

## 🛠 技术栈

**AI 应用**

![Eino](https://img.shields.io/badge/Eino_Agent-4B32C3?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square)
![Langfuse](https://img.shields.io/badge/Langfuse-0A0A0A?style=flat-square)
![Tool Calling](https://img.shields.io/badge/Tool_Calling-555555?style=flat-square)
![JSON Schema](https://img.shields.io/badge/JSON_Schema-000000?style=flat-square&logo=json&logoColor=white)

**后端**

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Gin](https://img.shields.io/badge/Gin-008ECF?style=flat-square&logo=gin&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-244c5a?style=flat-square&logo=grpc&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white)

**云原生与可观测性**

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=flat-square&logo=helm&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Nacos](https://img.shields.io/badge/Nacos-1E88E5?style=flat-square)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![Sentry](https://img.shields.io/badge/Sentry-362D59?style=flat-square&logo=sentry&logoColor=white)

**前端**

![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![TanStack Query](https://img.shields.io/badge/TanStack_Query-FF4154?style=flat-square&logo=reactquery&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)

---

## 📦 开源项目

| 项目 | 说明 | 技术 |
|---|---|---|
| [**resume-ai-builder**](https://github.com/cian-lien/resume-ai-builder) | AI 辅助的简历编辑器 | Vue · AI |
| [**candlex**](https://github.com/cian-lien/candlex) | 专业级 K 线（蜡烛图）组件 | Dart · Flutter |
| [**matrix**](https://github.com/cian-lien/matrix) | 用 Rust 构建的大型前端脚手架 | Rust |
| [**web-live2d-previewer**](https://github.com/cian-lien/web-live2d-previewer) | Live2D 模型网页预览器 | Python |

## 🌱 开源贡献

- [**Codewhale**](https://github.com/codewhale-hq/Codewhale)（GitHub 26k+ Stars）：修复 Bug 并提交 PR，已合入主仓库 → [PR #1992](https://github.com/codewhale-hq/Codewhale/pull/1992)

## 🧭 成长路线

- **2021** 开始自学前端
- **2023** 学习 Java，入门后端
- **2024** 开始学习 AI Agent 开发
- **2025** 第一家公司做实习前端开发
- **2026** 独立负责 Go 后端与 AI Agent 链路
