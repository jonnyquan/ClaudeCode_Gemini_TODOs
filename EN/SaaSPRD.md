# BitAgent SaaS Platform - Product Requirements Document (PRD)

**Version:** 1.1 (Detailed)
**Date:** July 4, 2025
**Author:** GeminiAgent (AI Development Partner)
**Approver:** Jonny (Project Owner)
**Status:** Draft

---

## 1. Product Overview

### 1.1. Product Vision
Transform BitAgent from a professional internal trading system into a leading, AI-driven automated trading SaaS platform for global quantitative traders and investment institutions. Our goal is to enable users—regardless of programming background—to easily build, backtest, deploy, and manage institutional-grade AI trading strategies, gaining a competitive edge in complex financial markets.

### 1.2. Background & Problem Statement
Current trading tools are polarized: some are complex frameworks for professional developers with steep learning curves, while others are “one-click copy trading” platforms for retail users, lacking flexibility and depth. BitAgent SaaS aims to fill this gap, providing advanced traders and small-to-medium investment teams with a **powerful yet user-friendly** “AI trading headquarters.”

### 1.3. Market Opportunity
As digital asset markets mature, more individuals and institutions seek smarter, more automated trading solutions. A SaaS platform that offers AI empowerment, flexible configuration, and controllable risk has huge market potential.

---

## 2. Target Audience

#### 2.1. **Crypto Pro - Mr. Chen**
- **Background**: Full-time crypto trader with 3-5 years of experience, managing 6-7 figure funds.
- **Pain Point**: “I have many trading ideas, but turning them into stable, 24/7 bots is too hard. I need a platform that lets me focus on strategy, not code and servers.”
- **Core Needs**: Powerful strategy builder, reliable backtesting engine, fine-grained risk control, and real-time P&L monitoring.

#### 2.2. **Tech-Savvy Investor - Ms. Li**
- **Background**: Busy tech executive, allocates crypto as part of her portfolio.
- **Pain Point**: “I believe AI can do better than me, but I don’t know where to start. Copy-trading products feel opaque and risky.”
- **Core Needs**: Clear interface, a “strategy marketplace” with vetted strategies, one-click deployment, and transparent performance reports.

---

## 3. Core Features - V1.0 (MVP)

### 3.1. User Authentication & Account Center
- **Description**: Secure user registration, login, and account management.
- **User Stories**:
    - **As a new user**, I want to quickly register with email and password to start using the platform.
    - **As a user**, I want to log in securely and reset my password if needed.
    - **As a security-conscious user**, I want to enable 2FA to protect my assets and strategies.
    - **As a logged-in user**, I want to view and manage my subscription, billing history, and profile.
- **Acceptance Criteria**:
    - [ ] Users can register with a unique email address.
    - [ ] Login page includes “forgot password” with email reset link.
    - [ ] Users can bind Google Authenticator or similar in account settings.
    - [ ] 2FA required for login after enabling.
    - [ ] Account center clearly shows subscription level, expiry, and upgrade options.

### 3.2. Exchange Connector
- **Description**: Securely connect users’ external exchange accounts for trading and data access.
- **User Stories**:
    - **As a user**, I want to enter my exchange API Key and Secret in a secure interface to connect my Binance/OKX account.
    - **As a user**, I want to see a clear list of my connected accounts and their status (e.g., connected, invalid key).
    - **As a user**, I can edit or delete any connected exchange account at any time.
- **Acceptance Criteria**:
    - [ ] Supports Binance and OKX spot and perpetual accounts.
    - [ ] API keys are encrypted in transit and at rest.
    - [ ] New API keys are validated immediately for permissions (“read info” and “trade allowed”).
    - [ ] API Secret Key is never shown in plaintext on the frontend.
    - [ ] Deleting an exchange connection safely pauses all associated running bots.

### 3.3. AI Strategy Builder
- **Description**: The product’s core—a visual interface for users to build trading strategies like building blocks.
- **User Stories**:
    - **As a strategy creator**, I can start from a blank canvas or a simple template (e.g., golden cross/death cross).
    - **As a strategy creator**, I can drag “data source” modules (e.g., BTC/USDT 15min K-line), “logic” modules (e.g., IF, moving average), and “action” modules (e.g., open long, close position) onto the canvas.
    - **As a strategy creator**, I can connect these modules to form a complete logic flow.
    - **As a strategy creator**, I can configure each module’s parameters (e.g., MA period, order size) in a right-side panel.
    - **As a strategy creator**, I can set global risk controls (e.g., max position size, pause strategy if total loss hits 5%).
- **Acceptance Criteria**:
    - [ ] At least 5 data source modules (K-line, funding rate, etc.).
    - [ ] At least 10 logic/indicator modules (SMA, EMA, RSI, MACD, IF/ELSE, etc.).
    - [ ] Core action modules (open, close, set TP/SL).
    - [ ] Modules can be connected via drag-and-drop to form clear logic lines.
    - [ ] System validates strategy completeness (e.g., no orphan modules) before saving.
    - [ ] Users can name and describe each strategy.

### 3.4. Backtesting Engine
- **Description**: Powerful historical backtesting before deployment to evaluate strategy performance.
- **User Stories**:
    - **As a strategy designer**, after building a strategy, I can select a historical period (e.g., last 6 months) and initial capital for backtesting.
    - **As a backtest user**, I get a clear, visual backtest report after completion.
    - **As an analyst**, I want reports with key performance charts: equity curve, return distribution, max drawdown.
- **Acceptance Criteria**:
    - [ ] Users can select preset time ranges (1m, 3m, 1y) or custom dates.
    - [ ] Backtest report includes: total return, annualized return, Sharpe ratio, Sortino ratio, max drawdown, win rate, profit/loss ratio.
    - [ ] Report lists all historical trades (buy/sell time, price, size, fee, P&L).
    - [ ] Buy/sell points are clearly marked on K-line charts.

### 3.5. Live Trading Dashboard
- **Description**: The central command center for monitoring all bots and account performance.
- **User Stories**:
    - **As a platform user**, I want to see total account net value (in USDT or USD) and today’s change on login.
    - **As a bot admin**, I want a card list of all strategy bots, each showing name, strategy, account, runtime, cumulative P&L, and status.
    - **As a bot admin**, I can start, pause, or stop any bot.
    - **As a trader**, I want a real-time area showing all trading signals and execution logs.
- **Acceptance Criteria**:
    - [ ] Total net value refreshes every 5 minutes.
    - [ ] Bot card status and P&L update near real-time (<30s delay).
    - [ ] “Stop” triggers a confirmation dialog, warning that all positions will be closed.
    - [ ] Trade logs can be filtered by bot name or exchange account.

---

## 4. Business Model

Tiered subscription, Freemium to attract initial users.

| Feature/Tier | **Freemium** | **Pro** | **Institutional** |
| :--- | :--- | :--- | :--- |
| **Price** | $0 | $99 / month | Custom |
| **Exchange Accounts** | 1 | 5 | Unlimited |
| **Concurrent Bots** | 1 | 10 | Unlimited |
| **Backtests/day** | 10 | 100 | Unlimited |
| **Strategy Market** | Free strategies | All strategies | All strategies |
| **AI Strategy Generation** | ❌ | ✅ (5/mo) | ✅ (unlimited) |
| **AI Parameter Optimization** | ❌ | ✅ (5/mo) | ✅ (unlimited) |
| **API Access** | ❌ | ✅ | ✅ |
| **Dedicated Support** | Community | Email | Account manager & tech support |

---

## 5. Tech Stack & Architecture

- **Frontend**: React / Next.js (for great DX and performance), TypeScript, Tailwind CSS.
- **Backend**: Python (reuse existing `bitagent` core), FastAPI (high-performance API framework).
- **Database**: PostgreSQL (relational), InfluxDB (time-series for K-line and indicators).
- **Queue/Cache**: Redis (for caching, task queue, and real-time agent messaging).
- **Deployment**: Docker + Kubernetes, deployed on AWS/GCP/Azure.
- **Core Principle**: Microservices architecture—user management, strategy builder, backtesting, live trading, etc. are decoupled for scalability and maintainability.

---

## 6. Go-to-Market Strategy

1.  **Alpha Test (1-2 months)**: Invite 20-30 core community members or professional traders for free, in-depth feedback.
2.  **Beta Public Test (2-3 months)**: Open registration, offer limited free and full-featured Pro trial, collect broader feedback, polish product.
3.  **Official Launch**: Release on Product Hunt, Hacker News, etc. Partner with crypto KOLs and media for promotion.
4.  **Content Marketing**: Consistently publish high-quality blogs and video tutorials—platform usage, quant trading knowledge, market analysis—to build authority.

---

## 7. Success Metrics

- **User Growth**: MAU > 1,000 (6 months post-launch)
- **Revenue**: MRR > $10,000 (6 months post-launch)
- **User Retention**: Paid churn rate < 5%
- **Product Value**: At least 30% of active users log in daily

---

## 8. Out of Scope for V1

To ensure high-quality, timely delivery of V1 (MVP), the following are **not** included in the first release:
- **Strategy Marketplace**: Only official templates, no community contributions in V1.
- **Social Trading/Copy Trading**: Complex account/profit-sharing logic postponed.
- **Mobile App**: V1 focuses on top-tier web experience.
- **Fiat On/Off Ramp**: Users’ funds remain on their own exchange accounts; platform does not touch user assets.
- **Multi-language Support**: V1 offers only English and Chinese interfaces.

---
*This document is the core guide for BitAgent SaaS platform development. All development activities should revolve around the requirements defined herein.*
