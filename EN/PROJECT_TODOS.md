# BitAgent SaaS - TODO List (Alpha Sprint)

## 🔴 P0 - Urgent Tasks (Must Complete This Week)
- [ ] [AUTH-001] Design user authentication database schema (users, credentials, 2fa_secrets)
- [ ] [AUTH-002] Implement user registration API (email/password)
- [ ] [AUTH-003] Implement user login API (returns JWT token)
- [ ] [WEB-001] Create basic registration and login pages

## 🟡 P1 - Current Tasks (This Month)
### Phase 1: Infrastructure & User System
- [ ] [AUTH-004] Implement JWT token verification middleware
- [ ] [AUTH-005] Implement "forgot password" flow (send reset link via email)
- [ ] [AUTH-006] Implement 2FA (Google Authenticator) binding and verification API
- [ ] [CONN-001] Design exchange key database schema (exchange_connections)
- [ ] [CONN-002] Implement secure exchange API Key add/verify/encrypted storage API
- [ ] [CONN-003] Implement API to get/delete connected exchanges
- [ ] [WEB-002] Create account center page with integrated 2FA binding
- [ ] [WEB-003] Create exchange connector page with key add/delete functionality
- [ ] [INFRA-001] Write Dockerfile for backend and frontend service containerization
- [ ] [INFRA-002] Set up basic CI/CD pipeline (e.g., GitHub Actions) for automated testing and deployment to dev environment

## 🔵 P2 - Planned Tasks (Next Month)
### Phase 2: Core Trading Features
- [ ] [BUILDER-001] Design core data structures for AI strategy builder
- [ ] [BUILDER-002] Develop backend API for strategy builder (save/load strategies)
- [ ] [WEB-004] Develop frontend visual interface for strategy builder (canvas, module drag & drop)
- [ ] [BACKTEST-001] Design backtest task queue and result storage scheme
- [ ] [BACKTEST-002] Develop backtesting engine API
- [ ] [WEB-005] Develop frontend for backtest report display
- [ ] [DASH-001] Design backend data aggregation API for live trading dashboard
- [ ] [WEB-006] Develop frontend for live trading dashboard

---
*Last updated: 2025-07-04*
*Owner: GeminiAgent*
*Note: This task list has been fully restructured according to SaasPRD.md V1.1 and the new product roadmap.*
