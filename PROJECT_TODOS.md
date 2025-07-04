# BitAgent SaaS - TODO 列表 (Alpha 版本冲刺)

## 🔴 P0 - 紧急任务 (本周必须完成)
- [ ] [AUTH-001] 设计用户认证数据库 Schema (users, credentials, 2fa_secrets)
- [ ] [AUTH-002] 实现用户注册API (邮箱/密码)
- [ ] [AUTH-003] 实现用户登录API (返回 JWT token)
- [ ] [WEB-001] 创建基础的注册和登录页面

## 🟡 P1 - 当前任务 (本月)
### Phase 1: 基础设施与用户体系
- [ ] [AUTH-004] 实现 JWT token 的验证中间件
- [ ] [AUTH-005] 实现“忘记密码”流程 (邮件发送重置链接)
- [ ] [AUTH-006] 实现 2FA (Google Authenticator) 的绑定与验证 API
- [ ] [CONN-001] 设计交易所密钥数据库 Schema (exchange_connections)
- [ ] [CONN-002] 实现安全的交易所 API Key 添加/验证/加密存储的 API
- [ ] [CONN-003] 实现获取/删除已连接交易所的 API
- [ ] [WEB-002] 创建账户中心页面，集成 2FA 绑定功能
- [ ] [WEB-003] 创建交易所连接器页面，集成密钥添加/删除功能
- [ ] [INFRA-001] 编写 Dockerfile 用于后端和前端服务的容器化
- [ ] [INFRA-002] 建立基础的 CI/CD 流水线 (e.g., GitHub Actions)，实现自动化测试和部署到开发环境

## 🔵 P2 - 计划任务 (下月)
### Phase 2: 核心交易功能
- [ ] [BUILDER-001] 设计 AI 策略构建器的核心数据结构
- [ ] [BUILDER-002] 开发策略构建器后端 API (保存/加载策略)
- [ ] [WEB-004] 开发策略构建器前端可视化界面 (画布、模块拖拽)
- [ ] [BACKTEST-001] 设计回测任务队列和结果存储方案
- [ ] [BACKTEST-002] 开发回测引擎 API
- [ ] [WEB-005] 开发回测报告前端展示页面
- [ ] [DASH-001] 设计实盘仪表盘后端数据聚合 API
- [ ] [WEB-006] 开发实盘仪表盘前端页面

---
*最后更新: 2025-07-04*
*负责人: GeminiAgent*
*说明: 此任务列表已根据 SaasPRD.md V1.1 和新的产品路线图全面重构。*
