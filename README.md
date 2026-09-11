# HN Pocket

### Know where your money goes.

HN Pocket is a lightweight personal finance and productivity application designed to make everyday money management simple.

Track expenses, organize spending, set monthly budgets, and understand your financial habits through clear, uncomplicated analytics.

HN Pocket is intentionally **not** a full accounting platform.

It focuses on one simple workflow:

> **Record → Organize → Budget → Understand**

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Node](https://img.shields.io/badge/node-20%2B-brightgreen.svg)
![Status](https://img.shields.io/badge/status-in%20development-orange.svg)

---

## Table of Contents

- [Why HN Pocket?](#-why-hn-pocket)
- [Core Features](#-core-features)
- [Categories](#-categories)
- [Monthly Budgets](#-monthly-budgets)
- [Simple Analytics](#-simple-analytics)
- [Dashboard](#-dashboard)
- [Transactions](#-transactions)
- [Spending Goals](#-spending-goals)
- [Income Tracking](#-income-tracking)
- [Recurring Transactions](#-recurring-transactions)
- [Mobile First](#-mobile-first)
- [Authentication](#-authentication)
- [REST API](#-rest-api)
- [Architecture](#️-architecture)
- [Technology Stack](#️-technology-stack)
- [Project Structure](#-project-structure)
- [Data Model](#️-data-model)
- [Security](#-security)
- [Testing](#-testing)
- [Local Development](#-local-development)
- [API Documentation](#-api-documentation)
- [Financial Disclaimer](#️-financial-disclaimer)
- [Roadmap](#️-roadmap)
- [Product Philosophy](#-product-philosophy)
- [Contributing](#-contributing)
- [License](#-license)

---

# ✨ Why HN Pocket?

Personal finance applications often become complicated very quickly.

Investments, loans, taxes, bank synchronization, portfolios, credit scores, insurance, and dozens of other features can make a simple question difficult to answer:

> **"Where did my money go this month?"**

HN Pocket focuses on answering that question.

### HN Pocket provides:

* 💸 Fast expense tracking
* 🏷️ Custom categories
* 📅 Monthly budgets
* 📊 Simple analytics
* 🎯 Spending goals
* 🔎 Transaction search
* 📱 Mobile-friendly experience
* 🔐 Private user accounts
* ⚡ Lightweight interface

No bank account connection is required.

Users manually record their transactions and remain in control of their financial data.

---

# 🚀 Core Features

## 💸 Expense Tracking

Record expenses quickly with the information that actually matters.

Each expense can contain:

* Amount
* Category
* Date
* Description
* Payment method
* Notes
* Tags

Example:

```text
┌──────────────────────────────────┐
│ 🍔 Food                          │
│                                  │
│ ₹420                             │
│ Dinner with friends              │
│                                  │
│ September 11, 2026               │
└──────────────────────────────────┘
```

The goal is to make adding an expense take only a few seconds.

---

# 🏷️ Categories

Expenses can be organized into customizable categories.

Default categories may include:

```text
Food
Transport
Shopping
Entertainment
Bills
Health
Education
Travel
Subscriptions
Other
```

Users can create their own categories as well.

Each category can have:

* Name
* Description
* Icon
* Budget
* Status

Example:

```text
Food
├── Groceries
├── Restaurants
└── Coffee
```

---

# 📅 Monthly Budgets

Set spending limits for individual categories or for the entire month.

Example:

```text
September 2026

Overall Budget
₹30,000 / ₹40,000

Food
₹6,200 / ₹8,000

Transport
₹2,400 / ₹4,000

Entertainment
₹1,800 / ₹3,000
```

The dashboard should make it immediately obvious:

* How much has been spent
* How much remains
* Which categories are approaching their limits
* Which categories have exceeded their budgets

---

# 📊 Simple Analytics

HN Pocket provides lightweight analytics designed for understanding spending behavior.

### Monthly overview

```text
September

Income       ₹50,000
Expenses     ₹31,450
Remaining    ₹18,550
```

### Spending breakdown

```text
Food              28%
Transport         14%
Shopping          19%
Bills             21%
Entertainment     10%
Other              8%
```

### Trends

Users can compare:

* Current month vs previous month
* Category spending
* Daily spending
* Weekly spending
* Monthly totals

Analytics should remain intentionally simple.

The purpose isn't to turn the application into a financial reporting suite.

---

# 📈 Dashboard

The dashboard is the primary entry point after login.

A typical dashboard contains:

```text
┌─────────────────────────────────────────────┐
│ September 2026                              │
│                                             │
│ Total Spent          Remaining              │
│ ₹31,450              ₹18,550                │
│                                             │
├─────────────────────────────────────────────┤
│                                             │
│ Monthly Budget                              │
│ ███████████████░░░░░░░░  78%                │
│                                             │
├─────────────────────────────────────────────┤
│                                             │
│ Recent Transactions                          │
│                                             │
│ 🍔 Food              -₹420                  │
│ 🚕 Transport         -₹180                  │
│ 🛍️ Shopping          -₹1,200                │
│ 📱 Subscription      -₹499                  │
│                                             │
└─────────────────────────────────────────────┘
```

The dashboard should answer the user's most important questions without requiring navigation.

---

# 🔎 Transactions

Users can browse their complete transaction history.

Supported functionality:

* Search
* Category filtering
* Date filtering
* Amount filtering
* Sorting
* Pagination

Example:

```http
GET /api/v1/transactions?category=food&month=2026-09
```

---

# 🎯 Spending Goals

HN Pocket can optionally support simple financial goals.

Examples:

```text
New Laptop
Target: ₹80,000
Saved: ₹42,500

█████████████░░░░░░░ 53%
```

Goals can represent:

* Purchases
* Savings targets
* Emergency funds
* Travel
* Personal milestones

Goals are deliberately kept separate from investment functionality.

---

# 💰 Income Tracking

Although the initial focus is expenses, HN Pocket can also track income.

Income entries may include:

* Salary
* Freelance
* Business
* Gifts
* Other

This enables a basic monthly picture:

```text
Income       ₹50,000
Expenses     ₹31,450
────────────────────
Balance      ₹18,550
```

---

# 🔄 Recurring Transactions

Users can define recurring expenses.

Examples:

```text
Netflix       ₹649      Monthly
Internet      ₹799      Monthly
Rent          ₹12,000   Monthly
Gym           ₹1,000    Monthly
```

Recurring transactions can automatically generate upcoming entries.

---

# 📱 Mobile First

HN Pocket is designed primarily around everyday usage.

The application should work naturally on:

* Mobile
* Tablet
* Desktop

Adding an expense should be particularly optimized for mobile.

The ideal interaction is:

```text
Open app
   ↓
+ Add Expense
   ↓
Enter amount
   ↓
Choose category
   ↓
Save
```

---

# 🔐 Authentication

Users have private accounts for managing their financial data.

Supported functionality:

* Registration
* Login
* Logout
* Session management
* Password reset
* Account settings

All financial records are scoped to the authenticated user.

A user must never be able to access another user's transactions.

---

# 🔌 REST API

HN Pocket exposes a REST API for the web application and future integrations.

Base URL:

```text
/api/v1
```

The API uses JSON for requests and responses.

---

## 👤 Authentication API

### Register

```http
POST /api/v1/auth/register
```

**Request**

```json
{
  "name": "Himayoun",
  "email": "user@example.com",
  "password": "secure-password"
}
```

### Login

```http
POST /api/v1/auth/login
```

**Request**

```json
{
  "email": "user@example.com",
  "password": "secure-password"
}
```

**Response**

```json
{
  "success": true,
  "data": {
    "user": {
      "id": "usr_82jd9",
      "name": "Himayoun",
      "email": "user@example.com"
    }
  }
}
```

### Get Current User

```http
GET /api/v1/auth/me
```

Returns the currently authenticated user.

### Logout

```http
POST /api/v1/auth/logout
```

Invalidates the current session.

---

## 💸 Transactions API

### Create Transaction

```http
POST /api/v1/transactions
```

**Request**

```json
{
  "type": "expense",
  "amount": 420,
  "categoryId": "cat_food",
  "description": "Dinner",
  "date": "2026-09-11"
}
```

### Get Transactions

```http
GET /api/v1/transactions
```

Query parameters:

| Param | Description |
|---|---|
| `page` | Page number for pagination |
| `limit` | Results per page |
| `type` | `income` or `expense` |
| `category` | Filter by category ID |
| `startDate` | Range start (`YYYY-MM-DD`) |
| `endDate` | Range end (`YYYY-MM-DD`) |
| `search` | Free-text search on description/notes |
| `sort` | Sort field/direction, e.g. `date:desc` |

Example:

```http
GET /api/v1/transactions?startDate=2026-09-01&endDate=2026-09-30
```

### Get Transaction

```http
GET /api/v1/transactions/:transactionId
```

### Update Transaction

```http
PATCH /api/v1/transactions/:transactionId
```

### Delete Transaction

```http
DELETE /api/v1/transactions/:transactionId
```

---

## 🏷️ Categories API

### Create Category

```http
POST /api/v1/categories
```

**Request**

```json
{
  "name": "Food",
  "icon": "utensils"
}
```

### Get Categories

```http
GET /api/v1/categories
```

### Update Category

```http
PATCH /api/v1/categories/:categoryId
```

### Delete Category

```http
DELETE /api/v1/categories/:categoryId
```

---

## 📅 Budget API

### Create Budget

```http
POST /api/v1/budgets
```

**Request**

```json
{
  "month": "2026-09",
  "amount": 40000
}
```

### Get Current Budget

```http
GET /api/v1/budgets/current
```

### Set Category Budget

```http
POST /api/v1/budgets/category
```

**Request**

```json
{
  "categoryId": "cat_food",
  "month": "2026-09",
  "amount": 8000
}
```

### Update Budget

```http
PATCH /api/v1/budgets/:budgetId
```

### Delete Budget

```http
DELETE /api/v1/budgets/:budgetId
```

---

## 📊 Analytics API

### Monthly Summary

```http
GET /api/v1/analytics/monthly
```

Example:

```http
GET /api/v1/analytics/monthly?month=2026-09
```

**Response**

```json
{
  "month": "2026-09",
  "income": 50000,
  "expenses": 31450,
  "balance": 18550,
  "budget": 40000
}
```

### Category Breakdown

```http
GET /api/v1/analytics/categories
```

Returns spending grouped by category.

### Spending Trends

```http
GET /api/v1/analytics/trends
```

Returns spending data over a specified time period.

---

## 🎯 Goals API

### Create Goal

```http
POST /api/v1/goals
```

**Request**

```json
{
  "name": "New Laptop",
  "targetAmount": 80000,
  "deadline": "2027-03-01"
}
```

### Get Goals

```http
GET /api/v1/goals
```

### Get Goal

```http
GET /api/v1/goals/:goalId
```

### Update Goal

```http
PATCH /api/v1/goals/:goalId
```

### Delete Goal

```http
DELETE /api/v1/goals/:goalId
```

---

## 🔁 Recurring Transactions API

### Create Recurring Transaction

```http
POST /api/v1/recurring-transactions
```

**Request**

```json
{
  "description": "Internet",
  "amount": 799,
  "categoryId": "cat_bills",
  "frequency": "monthly",
  "nextOccurrence": "2026-10-01"
}
```

### Get Recurring Transactions

```http
GET /api/v1/recurring-transactions
```

### Update Recurring Transaction

```http
PATCH /api/v1/recurring-transactions/:id
```

### Delete Recurring Transaction

```http
DELETE /api/v1/recurring-transactions/:id
```

---

# 🏗️ Architecture

HN Pocket follows a modular full-stack architecture.

```text
                    ┌─────────────────────┐
                    │      Web App        │
                    │                     │
                    │ Dashboard           │
                    │ Transactions        │
                    │ Budgets             │
                    │ Analytics           │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      REST API       │
                    │                     │
                    │ Auth                │
                    │ Transactions        │
                    │ Categories          │
                    │ Budgets             │
                    │ Analytics           │
                    │ Goals               │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │     PostgreSQL      │
                    │                     │
                    │ Users               │
                    │ Transactions        │
                    │ Categories          │
                    │ Budgets             │
                    │ Goals               │
                    └─────────────────────┘
```

---

# 🛠️ Technology Stack

## Frontend

* Next.js
* React
* TypeScript
* Tailwind CSS
* shadcn/ui

## Backend

* Node.js
* Express.js
* TypeScript

## Database

* PostgreSQL
* Prisma ORM

## Authentication

* Secure session-based authentication
* Password hashing

## Infrastructure

* Docker
* GitHub Actions
* CI/CD

The architecture is intentionally straightforward so the project can remain easy to develop, test, deploy, and maintain.

---

# 📁 Project Structure

```text
hn-pocket/
│
├── apps/
│   ├── web/
│   │   ├── app/
│   │   ├── components/
│   │   ├── features/
│   │   │   ├── dashboard/
│   │   │   ├── transactions/
│   │   │   ├── budgets/
│   │   │   ├── analytics/
│   │   │   └── goals/
│   │   └── lib/
│   │
│   └── api/
│       ├── src/
│       │   ├── modules/
│       │   │   ├── auth/
│       │   │   ├── transactions/
│       │   │   ├── categories/
│       │   │   ├── budgets/
│       │   │   ├── analytics/
│       │   │   ├── goals/
│       │   │   └── recurring/
│       │   │
│       │   ├── middleware/
│       │   ├── routes/
│       │   └── config/
│       │
│       └── tests/
│
├── packages/
│   ├── types/
│   ├── validation/
│   └── ui/
│
├── prisma/
│   ├── schema.prisma
│   └── migrations/
│
├── docs/
│
├── docker/
│
├── .github/
│   └── workflows/
│
├── package.json
└── README.md
```

---

# 🗄️ Data Model

The core data model is intentionally small.

```text
User
 │
 ├── Transaction
 │       ├── Category
 │       └── PaymentMethod
 │
 ├── Budget
 │       └── Category
 │
 ├── Goal
 │
 └── RecurringTransaction
```

### Core entities

| Entity               | Purpose                            |
| --------------------- | ------------------------------------ |
| User                  | Account owner                        |
| Transaction           | Income or expense record             |
| Category              | Spending classification              |
| Budget                | Spending limit                       |
| Goal                  | Savings target                       |
| RecurringTransaction  | Automated recurring expense/income   |

---

# 🔒 Security

Financial information is private user data, so authorization is critical.

HN Pocket should implement:

* Secure password hashing
* Session management
* Authentication middleware
* Authorization checks
* Request validation
* Rate limiting
* Input sanitization
* Secure HTTP headers
* Database constraints
* User-level data isolation
* Audit logging for sensitive operations

Every transaction query must be scoped to the authenticated user.

For example:

```text
User A
   │
   └── Transactions A

User B
   │
   └── Transactions B
```

User A must never be able to retrieve User B's financial records by changing an ID in an API request.

---

# 🧪 Testing

Critical financial calculations should have automated tests.

### Unit Tests

```bash
npm run test
```

Examples:

* Budget calculations
* Monthly totals
* Category aggregation
* Balance calculations
* Recurrence calculations

### Integration Tests

```bash
npm run test:integration
```

### End-to-End Tests

Important flows:

```text
Register
   ↓
Login
   ↓
Create Category
   ↓
Add Expense
   ↓
Create Budget
   ↓
View Dashboard
   ↓
Review Analytics
```

```bash
npm run test:e2e
```

---

# 🚀 Local Development

## Requirements

* Node.js 20+
* PostgreSQL 15+
* npm / pnpm
* Git

## Installation

Clone the repository:

```bash
git clone https://github.com/hnpocket/hn-pocket.git
```

Navigate into the project:

```bash
cd hn-pocket
```

Install dependencies:

```bash
npm install
```

Create your environment file:

```bash
cp .env.example .env
```

Configure:

```env
# PostgreSQL connection string, e.g. postgresql://user:pass@localhost:5432/hnpocket
DATABASE_URL=

# Secret used to sign sessions/auth tokens — use a long random string
AUTH_SECRET=

# Base URLs for the API and web app
API_URL=
WEB_URL=
```

Run migrations:

```bash
npx prisma migrate dev
```

Start development:

```bash
npm run dev
```

---

# 📖 API Documentation

API documentation is exposed through OpenAPI.

Development:

```text
/api/docs
```

The API specification provides:

* Endpoint descriptions
* Request schemas
* Response schemas
* Authentication requirements
* Error responses
* Example requests

---

# ⚠️ Financial Disclaimer

HN Pocket is a personal finance tracking and budgeting application.

It is **not** a bank, financial institution, investment platform, tax service, or financial advisor.

HN Pocket does not provide financial advice or guarantee the accuracy of manually entered financial information.

Users are responsible for verifying their own financial records.

---

# 🗺️ Roadmap

## Phase 1 — Foundation

* [x] Project setup
* [ ] Authentication
* [ ] User profile
* [ ] Transaction CRUD
* [ ] Categories
* [ ] Dashboard
* [ ] Monthly totals

## Phase 2 — Budgeting

* [ ] Monthly budgets
* [ ] Category budgets
* [ ] Budget progress
* [ ] Spending warnings
* [ ] Budget history

## Phase 3 — Insights

* [ ] Spending breakdown
* [ ] Monthly comparisons
* [ ] Spending trends
* [ ] Custom date ranges
* [ ] Dashboard analytics

## Phase 4 — Productivity

* [ ] Financial goals
* [ ] Recurring transactions
* [ ] Transaction notes
* [ ] Tags
* [ ] Quick-add experience

## Phase 5 — Data & Integrations

* [ ] CSV import
* [ ] CSV export
* [ ] Backup/restore
* [ ] API keys
* [ ] Public API documentation

## Future Considerations

These features are intentionally **not part of the initial product scope**:

* Bank account synchronization
* Investment tracking
* Stock portfolios
* Cryptocurrency tracking
* Credit score monitoring
* Loans
* Tax preparation

The project may explore these areas later, but HN Pocket's core identity remains **simple personal money management**.

---

# 🎯 Product Philosophy

HN Pocket is built around a simple idea:

> **Personal finance software should help you understand your money, not make managing it feel like a second job.**

Every feature should make one of these actions easier:

```text
Track
  ↓
Organize
  ↓
Budget
  ↓
Understand
  ↓
Improve
```

HN Pocket intentionally prioritizes:

### Simplicity over feature count

A smaller set of useful features is better than a dashboard filled with information nobody uses.

### Manual control over unnecessary integrations

Users should be able to use HN Pocket without connecting their bank accounts.

### Useful analytics over complicated reports

The application should explain spending patterns without requiring users to understand financial reporting.

### Privacy by default

Financial information belongs to the user.

---

# 🤝 Contributing

Contributions are welcome.

Before submitting a pull request:

1. Open an issue describing the proposed change.
2. Create a feature branch.
3. Implement the change.
4. Add or update tests.
5. Run the test suite.
6. Verify the application builds.
7. Open a pull request.

Example:

```bash
git checkout -b feature/budget-alerts
```

```bash
git commit -m "feat: add budget alerts"
```

```bash
git push origin feature/budget-alerts
```

---

# 📜 License

HN Pocket is licensed under the **MIT License**.

See [`LICENSE`](./LICENSE) for details.

---

<p align="center">
  Built with ❤️ for people who just want to know where their money went.
</p>
