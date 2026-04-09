# Nova - 企业级 CRM 应用平台

[![CI](https://github.com/zksongsong/nova/actions/workflows/ci.yml/badge.svg)](https://github.com/zksongsong/nova/actions/workflows/ci.yml)
[![Security](https://github.com/zksongsong/nova/actions/workflows/security.yml/badge.svg)](https://github.com/zksongsong/nova/actions/workflows/security.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Nova 是一款面向企业的客户关系管理（CRM）应用平台，类似于 vtiger CRM，旨在帮助企业高效管理客户、销售、服务和市场营销活动。

## 🏗️ 技术架构

本项目采用**前后端分离**架构，结合 **AI 代码生成**与**多人协作开发**模式。

| 层级 | 技术选型 | 说明 |
|------|----------|------|
| **前端** | React + TypeScript + Ant Design Pro | 企业级中后台前端框架 |
| **后端** | Spring Boot 3 + Java 17 | 微服务架构后端框架 |
| **数据库** | PostgreSQL 15+ | 主数据库 |
| **缓存** | Redis 7+ | 缓存与会话管理 |
| **搜索** | Elasticsearch (规划中) | 全文检索 |
| **消息队列** | RabbitMQ (规划中) | 异步任务处理 |

## 📁 项目结构

```
nova/
├── docs/                          # 项目文档
│   ├── architecture/              # 架构设计文档
│   ├── api/                       # API 文档（OpenAPI/Swagger）
│   ├── adr/                       # 架构决策记录（ADR）
│   └── prompts/                   # AI Prompt 模板
├── frontend/                      # 前端项目（React + TypeScript）
├── backend/                       # 后端项目（Spring Boot）
├── shared/                        # 前后端共享资源（类型定义、常量）
├── database/                      # 数据库相关
│   ├── migrations/                # 数据库迁移脚本
│   └── seeds/                     # 种子数据
├── deploy/                        # 部署配置
│   ├── docker/                    # Docker 配置
│   └── k8s/                       # Kubernetes 配置
├── .github/                       # GitHub 配置
│   ├── workflows/                 # CI/CD 流水线
│   ├── ISSUE_TEMPLATE/            # Issue 模板
│   ├── copilot-instructions.md    # Copilot 项目级指令
│   ├── PULL_REQUEST_TEMPLATE.md   # PR 模板
│   └── CODEOWNERS                 # 代码审查责任人
├── docker-compose.yml             # 本地开发环境
├── .env.example                   # 环境变量模板
├── .editorconfig                  # 编辑器配置
├── .gitignore                     # Git 忽略规则
├── CONTRIBUTING.md                # 贡献指南
├── CODING_STANDARDS.md            # 编码规范
├── LICENSE                        # 开源许可证
└── README.md                      # 项目说明
```

## 🚀 快速开始

### 环境要求

- Java 17+
- Node.js 18+
- Docker & Docker Compose
- Git

### 1. 克隆仓库

```bash
git clone https://github.com/zksongsong/nova.git
cd nova
```

### 2. 启动基础服务

```bash
# 复制环境变量模板
cp .env.example .env

# 启动 PostgreSQL 和 Redis
docker-compose up -d
```

### 3. 启动后端

```bash
cd backend
./mvnw spring-boot:run
```

### 4. 启动前端

```bash
cd frontend
npm install
npm run dev
```

## 📖 开发规范

- [编码规范](./CODING_STANDARDS.md) - 前后端编码标准
- [贡献指南](./CONTRIBUTING.md) - 开发流程与协作规范
- [架构决策记录](./docs/adr/) - 重要技术决策及其原因
- [AI Prompt 模板](./docs/prompts/) - 标准化 AI 代码生成模板

## 🤖 AI 辅助开发

本项目积极拥抱 AI 辅助开发，但有严格的质量管控：

1. AI 生成的代码必须使用 `ai/` 前缀的分支
2. 所有 AI 生成代码必须通过 CI 流水线检查
3. AI 生成代码需要至少 1 人进行专门的 Code Review
4. 项目已配置 [Copilot 指令](./.github/copilot-instructions.md) 确保生成代码符合项目规范

## 📄 许可证

本项目基于 [MIT 许可证](./LICENSE) 开源.