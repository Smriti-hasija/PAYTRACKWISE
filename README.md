# 💸 PayTrackWise
### Your Money. Your Goals. Your Financial Clarity.

<p align="center">
  <strong>An AI-powered personal finance management platform designed to turn everyday financial data into meaningful insights, smarter spending decisions, and better financial habits.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next.js-15-black?logo=next.js" />
  <img src="https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=black" />
  <img src="https://img.shields.io/badge/TypeScript-5.7-3178C6?logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-Backend-009688?logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/SQLite-Database-003B57?logo=sqlite&logoColor=white" />
  <img src="https://img.shields.io/badge/Ollama-Local_AI-111111" />
</p>

---

## 🌟 Overview

Managing money should not feel like solving a puzzle.

Between monthly expenses, recurring bills, income, savings goals, and unexpected purchases, it is easy to lose track of where money actually goes.

**PayTrackWise** aims to simplify personal financial management by bringing financial tracking, transaction management, intelligent analysis, and financial health insights together in one platform.

Instead of simply recording transactions, PayTrackWise helps users understand their financial behaviour through transaction-based analysis, AI-assisted insights, and a personalized financial overview.

The platform combines a modern web interface, a Python-based backend, persistent financial data storage, and locally running AI models.

### Our Vision

> Don't just track your money. Understand it, improve it, and make it work for you.

---

## 🎯 Problem Statement

Personal financial management is often fragmented and reactive.

People frequently face challenges such as:

- **Lack of Financial Visibility:** It is difficult to understand exactly how much money is coming in and going out.
- **Uncontrolled Spending:** Small and frequent purchases accumulate without users realizing their actual impact.
- **Disconnected Financial Records:** Income, expenses, and savings goals are often maintained across different applications or manually updated spreadsheets.
- **Limited Financial Insights:** Traditional expense trackers record transactions but may not explain spending patterns or highlight areas that need attention.
- **Difficulty Setting Financial Goals:** Users struggle to connect everyday spending decisions with long-term financial objectives.
- **Manual Receipt Management:** Extracting useful information from bills and receipts can be time-consuming.

The result is a lack of financial awareness, inconsistent saving habits, and difficulty making informed money decisions.

## 💡 Proposed Solution

PayTrackWise addresses these challenges through an integrated personal finance management platform.

It provides a centralized environment where users can:

1. Create an account and establish their financial profile.
2. Record and organize income and expenses.
3. Monitor financial activity through a unified transaction ledger.
4. Evaluate financial health using transaction-based scoring.
5. Generate AI-assisted financial summaries and recommendations.
6. Extract relevant information from receipts using OCR.
7. Maintain financial goals and personal financial preferences.

By combining structured financial records with intelligent analysis, PayTrackWise aims to transform raw financial information into understandable and actionable insights.

---

## ✨ Key Features

### 1. 🔐 User Authentication & Account Management

A dedicated account system that allows users to create and access their personal financial workspace.

- User registration and login.
- Email-based account identification.
- Password hashing with individual salts.
- Signed, time-limited authentication tokens.
- Session management.
- User-specific financial profiles.

### 2. 👤 Personalized Financial Onboarding

Every financial journey begins with understanding the user's financial situation.

During onboarding, users can provide:

- Personal name and city.
- Monthly income.
- Housing expenses.
- Financial goal name.
- Target savings amount.
- Financial alert preferences.

The onboarding information establishes the foundation for personalized financial analysis.

Monthly income can also be recorded as an initial credit transaction.

### 3. 💳 Transaction & Expense Management

A centralized ledger for recording and managing financial activities.

Each transaction can include:

- Merchant or transaction description.
- Expense category.
- Transaction date and time.
- Transaction amount.
- Transaction type (Credit or Debit).
- Payment method.

The system supports income and expense records, helping users understand their overall money movement.

### 4. 📊 Generic Financial Health Score

One of the key analytical components of PayTrackWise.

The platform calculates a transaction-based financial score on a scale of **300–900**.

The scoring logic considers factors such as:

- Transaction history.
- Money received versus money spent.
- Spending distribution across categories.
- Fixed financial commitments.
- Remaining money after expenses.

### 5. 🤖 AI-Powered Financial Insights

PayTrackWise integrates Ollama to provide locally running AI capabilities.

The AI insight engine can:

- Summarize financial information in simple language.
- Generate concise financial explanations.
- Help users understand their financial records.
- Produce contextual financial recommendations.
- Reuse cached insights when the AI service is unavailable.

The implementation supports configurable local models, with `llama3:8b` as the default.

### 6. 🧾 Smart Receipt Scanning & OCR

Manually entering receipt information can be tedious.

PayTrackWise includes a receipt-processing workflow that uses Optical Character Recognition (OCR) to extract information from supported receipt images.

The extraction process can identify:

- Merchant information.
- Invoice number.
- Bill date.
- Tax amount.
- Individual line items.
- Item descriptions and amounts.

The backend uses Tesseract OCR and includes image preprocessing to improve text readability.

Extracted receipt information is stored for reuse.

### 7. 💾 Persistent Financial Data Storage

The backend uses SQLite for local persistent storage.

The database maintains structured records for:

- User accounts.
- User profiles.
- Transactions.
- AI-generated insights.
- Receipt extraction records.
- Ledger snapshots.

Content hashing is used in the insight and receipt workflows to identify repeated content and support caching.

### 8. 🔄 Local Data Fallback

The frontend includes a browser-based local storage fallback for account and ledger workflows when the backend cannot be reached.

This helps preserve local user activity during development and provides an alternative to remote API-backed storage.

---

### Architecture Explanation

**1. Presentation Layer**

The Next.js frontend provides the user interface, account workflows, financial interactions, and application experience.

**2. Application Layer**

The FastAPI backend exposes REST endpoints and handles authentication, onboarding, transactions, receipt processing, and financial analysis.

**3. Business Logic Layer**

Dedicated services handle financial scoring, AI summaries, receipt processing, and other application operations.

**4. Persistence Layer**

SQLite stores account information, profiles, transactions, receipts, cached insights, and ledger snapshots.

**5. AI Layer**

Ollama provides local language-model inference for financial summaries and score recommendations.

---

## 🛠️ Technology Stack

| Layer | Technologies |
|---|---|
| Frontend Framework | Next.js 15 |
| UI Library | React 19 |
| Programming Language | TypeScript 5.7 |
| Styling | Tailwind CSS 3 |
| Animations | GSAP, @gsap/react |
| 3D Graphics | Three.js, React Three Fiber, Drei |
| Smooth Scrolling | Lenis |
| Icons | Lucide React |
| Backend Language | Python |
| Backend Framework | FastAPI |
| API Server | Uvicorn |
| Data Validation | Pydantic |
| Database | SQLite |
| AI Runtime | Ollama |
| AI Model | Llama 3 8B |
| Receipt Processing | Tesseract OCR |
| Image Processing | Pillow (optional enhancement) |
| Version Control | Git & GitHub |

---

## 🔄 Application Workflow

The general application workflow is:

1. **Account Creation:** The user registers or signs into PayTrackWise.
2. **Financial Onboarding:** The user provides income, housing expenses, and financial goals.
3. **Transaction Recording:** Income and expenses are recorded in the financial ledger.
4. **Data Processing:** The backend validates and stores financial information.
5. **Financial Analysis:** Transaction records are evaluated by the financial scoring engine.
6. **AI Processing:** Ollama can generate contextual summaries and recommendations.
7. **Receipt Processing:** Receipt images can be processed through the OCR workflow.
8. **Financial Understanding:** The user can access the resulting financial information through the application.

---

## 🗂️ Project Structure

```text
PAYTRACKWISE/
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   │   ├── __init__.py
│   │   │   └── routes.py
│   │   │
│   │   ├── core/
│   │   │   ├── db.py
│   │   │   └── security.py
│   │   │
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   │   ├── generic_score.py
│   │   │   ├── ollama.py
│   │   │   └── receipts.py
│   │   │
│   │   └── main.py
│   │
│   ├── data/
│   └── requirements
│
├── frontend/
│   ├── src/
│   │   ├── app/
│   │   ├── components/
│   │   ├── context/
│   │   ├── lib/
│   │   └── tests/
│   │
│   ├── package.json
│   ├── package-lock.json
│   ├── next.config.mjs
│   └── tsconfig.json
│
├── .gitignore
├── README.md
└── run.sh
```

## 🔌 API Endpoints

The backend exposes REST APIs for the main application workflows.

| Method | Endpoint | Description |
|---|---|---|
| POST | `/auth/signup` | Register a new user |
| POST | `/auth/signin` | Authenticate a user |
| GET | `/auth/me` | Retrieve the current account |
| PUT | `/onboarding` | Save financial onboarding information |
| POST | `/transactions` | Create a transaction |
| GET | `/transactions` | Retrieve transactions |
| POST | `/ai/summary` | Generate financial summaries |
| POST | `/ai/generic-score` | Calculate financial health score |
| POST | `/ocr/scan` | Process a receipt image |
| POST | `/ledger/snapshot` | Save a ledger snapshot |
| GET | `/health` | Check backend and Ollama status |

For interactive API exploration, visit:

`http://localhost:8000/docs`

---

## 🗄️ Database Design

PayTrackWise uses SQLite to maintain structured application data.

The database contains the following main tables:

| Table | Purpose |
|---|---|
| `users` | Stores user account credentials and basic details |
| `profiles` | Stores personal and financial onboarding information |
| `transactions` | Stores credit and debit records |
| `ai_insights` | Stores cached AI-generated summaries |
| `receipts` | Stores extracted receipt information |
| `ledger_snapshots` | Stores financial ledger snapshots |

The database is initialized automatically when the backend starts.

---

## 🔐 Security Considerations

Security is an important part of a financial application.

The current implementation includes:

- Password hashing using PBKDF2-HMAC-SHA256 with individual salts.
- HMAC-signed, time-limited bearer tokens.
- Authenticated account and transaction routes.
- Input validation using Pydantic.
- Parameterized SQL queries for database operations.
- Environment-based configuration for the authentication signing secret.

**Deployment note:** Configure a strong, unique `FINSHIELD_SECRET` before using the application outside a local development environment. The default development secret must not be used in production.

This project is a development-oriented personal finance application and should not be used to store real banking credentials or sensitive financial records without additional security hardening.

---

## 🚀 Future Enhancements

PayTrackWise has room to evolve into a more comprehensive personal financial ecosystem.

Potential improvements include:

- **Advanced Budget Planning:** Create category-wise budgets and monitor spending limits.
- **Recurring Expense Detection:** Identify recurring payments and subscriptions.
- **Savings Goal Tracking:** Monitor progress toward multiple financial goals.
- **Investment Portfolio Tracking:** Bring investments and asset allocation into the financial overview.
- **Debt & EMI Management:** Track loans, liabilities, and upcoming payments.
- **Advanced Financial Forecasting:** Estimate future expenses and savings using historical patterns.
- **Enhanced AI Recommendations:** Generate more contextual financial suggestions.
- **Data Visualization:** Introduce richer financial reports and interactive analytics.
- **Banking Integrations:** Explore secure integrations with supported financial data providers.
- **Exportable Reports:** Generate downloadable monthly and yearly financial reports.

These are planned enhancement areas, not claims that every feature is already implemented.

---

## 👩‍💻 Project Maintainer

**Smriti-hasija**

GitHub: [@Smriti-hasija](https://github.com/Smriti-hasija)

Project Repository: [PayTrackWise](https://github.com/Smriti-hasija/PayTrackWise)

---


<p align="center">
  <strong>PayTrackWise — Because every financial decision matters.</strong>
  <br/>
  <em>Track Smarter. Spend Better. Build Financial Confidence.</em>
</p>
