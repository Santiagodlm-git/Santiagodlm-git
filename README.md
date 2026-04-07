## Hello! Welcomme to my profile

I'm Santiago de la Mora Martinez
Currently studying Financial Engineering at ITESO, and working on a startup called BeWealth, that uses AI trained models to help the user in different ways


# 📈 BeWealth

> Personal investment management web platform with real-time technical analysis.

> **NOTE**
> **Can't find the repository?** This project does not live in my personal repositories, but inside the **BeWealth LLC** organization on GitHub. To access it, go to my profile [@SantiagodlM-git](https://github.com/SantiagodlM-git), look for the **Organizations** section in the bottom left and click on the **BeWealth** icon — that will take you directly to the organization and its repositories.

BeWealth is a full-stack application built for individual investors to manage their portfolios, track financial assets, and receive alerts based on technical indicators like RSI — all in one place.

---

## 🚀 Key Features

### 💼 Portfolio Management
- Create and manage multiple investment portfolios
- Track positions with entry price, current value, and performance
- Valuation in USD and MXN with real-time exchange rate
- Visualize asset distribution and profit/loss

### 📋 Watchlists
- Personalized watchlists per user
- Add and monitor stock symbols (equities, ETFs, etc.)
- Smart symbol search with autocomplete
- Automatic price and variation updates

### 🚨 RSI Alert System
- Automatic alerts based on the Relative Strength Index (RSI)
- **Buy** signals (RSI < 30 — oversold) and **Sell** signals (RSI > 70 — overbought)
- Real-time notification panel updated every minute
- Filter by signal type: Buy, Sell, Overbought, Oversold
- RSI vs SMA analysis for more precise signals

### 📊 Market Indicators
- Real-time monitoring of key indicators (USD/MXN, indices, etc.)
- Historical price data per symbol
- Technical analysis with multiple indicators per position

### 🔐 Authentication & Security
- Secure registration and login with bcrypt (12 salt rounds)
- JWT sessions via NextAuth
- Password recovery via email (SendGrid)
- Recovery tokens with 1-hour expiration
- Per-user data isolation

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Framework** | Next.js 15 (App Router) |
| **Frontend** | React 19, TypeScript, Tailwind CSS 4 |
| **Animations** | Framer Motion |
| **Charts** | Recharts |
| **Icons** | Lucide React |
| **Backend** | Next.js API Routes |
| **Database** | SQL Server (MSSQL) |
| **ORM/Driver** | mssql |
| **Auth** | NextAuth.js, JWT, bcrypt |
| **Email** | SendGrid |
| **UI Components** | Headless UI |

---

## 📁 Project Structure

```
BeWealthWeb/
├── src/
│   ├── app/                    # Pages and API Routes (Next.js App Router)
│   │   ├── dashboard/          # Main dashboard
│   │   ├── portfolio/          # Portfolio management
│   │   ├── watchlists/         # Watchlists
│   │   ├── alerts/             # RSI alert system
│   │   ├── symbols/            # Symbol search
│   │   ├── login/              # Authentication
│   │   ├── register/           # User registration
│   │   ├── forgot-password/    # Password recovery
│   │   └── api/                # Backend endpoints
│   ├── components/             # Reusable React components
│   │   ├── alerts/             # Alert components
│   │   ├── auth/               # Auth forms
│   │   ├── landing/            # Landing page sections
│   │   ├── layout/             # Navbar, Footer, Sidebar
│   │   ├── portfolio/          # Portfolio cards and tables
│   │   ├── portfolios/         # Portfolio modals
│   │   ├── positions/          # Position analysis
│   │   ├── watchlists/         # Watchlist tables and modals
│   │   └── ui/                 # Base components (Button, Card, Modal...)
│   ├── lib/                    # Server-side utilities
│   │   ├── auth.ts             # NextAuth config
│   │   ├── database.ts         # SQL Server connection
│   │   ├── email.ts            # Email service (SendGrid)
│   │   └── portfolio.ts        # Portfolio logic
│   ├── types/                  # TypeScript types
│   └── utils/                  # Financial calculations and utilities
├── Documents/                  # Database diagrams
└── Logo Files/                 # Logo assets (SVG, PNG, PDF)
```

---

## ⚙️ Installation & Setup

### Prerequisites
- Node.js 18+
- SQL Server (local or Docker)
- SendGrid account (for emails)

### 1. Clone the repository

```bash
git clone https://github.com/BeWealth-LLC/BeWealthWeb.git
cd BeWealthWeb
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set up environment variables

Create a `.env.local` file at the project root:

```env
# Database
DB_HOST=localhost
DB_PORT=1433
DB_NAME=BeWealth_NextJS
DB_USER=sa
DB_PASSWORD=your_password

# Authentication
NEXTAUTH_SECRET=your_secure_secret
NEXTAUTH_URL=http://localhost:3002

# Email (SendGrid)
SENDGRID_API_KEY=your_api_key
```

### 4. Create the database

Run the SQL scripts in SQL Server Management Studio in this order:

```bash
1. create-database.sql
2. create-stocks-table.sql
3. create-portafolios-table.sql
4. create-watchlists-table.sql
5. add-*.sql  # Additional migration scripts
```

### 5. Start the development server

```bash
npm run dev
```

The app will be available at [http://localhost:3002](http://localhost:3002)

---

## 📡 Main API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/rsi-alerts` | Active RSI alerts |
| `GET` | `/api/market-indicators` | Market indicators |
| `GET/POST` | `/api/portfolios` | Portfolio management |
| `GET/POST` | `/api/watchlists` | Watchlist management |
| `POST` | `/api/auth/forgot-password` | Request password recovery |
| `POST` | `/api/auth/reset-password` | Reset password |

---

## 🗄️ Database

BeWealth uses SQL Server with the following main tables:

- **`usuarios`** — System users with secure authentication
- **`portafolios`** — Investment portfolios per user
- **`posiciones`** — Positions within each portfolio
- **`watchlists`** — Personalized watchlists
- **`watchlist_items`** — Symbols within each watchlist
- **`stocks`** — Financial instruments catalog
- **`datos_diarios`** — Historical price data (OHLCV)
- **`alertas_cambio_grupos`** / **`alertas_cambio_items`** — Alert system
- **`IndicadoresMercado`** — Real-time indicators (USD/MXN, etc.)

---

## 🏢 Organization

Developed under **[BeWealth LLC](https://github.com/BeWealth-LLC)**

---

## 📄 License

© 2025 BeWealth. All rights reserved.
