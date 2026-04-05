# FinFlow — Finance Dashboard

A sleek, animated finance dashboard built with React. Dark by default, highly interactive, and fully responsive.

## Features

### Core
- **Dashboard Overview** — Net Balance, Income, Expenses, Savings Rate cards with animated hover effects
- **Area + Bar Charts** — Monthly income vs expense trends using Recharts
- **Pie/Donut Chart** — Categorical spending breakdown
- **Transactions Page** — Full table with search, filtering (month/type/category), sorting, and pagination
- **Insights Page** — Radar chart, horizontal bar chart, monthly deep-dive table, and 6 smart insight cards
- **Role-Based UI** — Admin can add/edit/delete transactions; Viewer sees read-only mode. Toggle via sidebar.
- **State Management** — React Context + useReducer for global state; localStorage persistence across sessions

### UX / Design
- **Dark / Light Mode toggle** — Smooth transition with CSS variables
- **Animated background blobs** — Three floating gradient orbs for depth
- **Card animations** — Staggered `cardIn` keyframes on load, hover lift + glow effects
- **Responsive** — Hamburger menu on mobile, grid reflows for all screen sizes
- **Export to CSV** — Download filtered transactions as a `.csv` file
- **Toast notifications** — react-hot-toast for all CRUD operations

## Quick Start

```bash
# 1. Install dependencies
npm install

# 2. Start the dev server
npm start

# 3. Open http://localhost:3000
```

## Project Structure

```
src/
├── context/
│   └── AppContext.jsx       # Global state (role, filters, transactions, theme)
├── data/
│   └── transactions.js      # Mock data + helper functions
├── components/
│   ├── Dashboard.jsx        # Layout shell
│   ├── Sidebar.jsx          # Navigation + role switcher + theme toggle
│   ├── Overview.jsx         # Main dashboard page
│   ├── Transactions.jsx     # Transactions table + CRUD modal
│   ├── Insights.jsx         # Charts + insight cards
│   └── styles.css           # All styles (CSS variables, animations, responsive)
├── App.jsx
└── index.js
```

## Role Switching

Toggle between **Admin** and **Viewer** in the sidebar bottom panel:

| Feature | Admin | Viewer |
|---------|-------|--------|
| View data | ✅ | ✅ |
| Add transactions | ✅ | ❌ |
| Edit transactions | ✅ | ❌ |
| Delete transactions | ✅ | ❌ |
| Export CSV | ✅ | ✅ |

## Tech Stack

- **React 18** — Functional components + hooks
- **Recharts** — AreaChart, BarChart, PieChart, RadarChart
- **React Context + useReducer** — State management
- **react-hot-toast** — Notifications
- **lucide-react** — Icons
- **Google Fonts** — Syne (headings) + DM Mono (code/labels) + Inter (body)
- **CSS Custom Properties** — Full dark/light theming via CSS variables

## Data Persistence

All state (transactions, filters, role, theme) is persisted to `localStorage` under the key `financeApp_v1`. Your data survives page refreshes.

## Responsive Breakpoints

- `> 1100px` — Full 4-column layout
- `768px–1100px` — 2-column cards, stacked charts
- `< 768px` — Single column, hamburger menu, simplified table
- `< 480px` — Full single column, vertical filters
