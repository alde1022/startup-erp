# Startup ERP

Modern ERP system for startups - lightweight, modular, cloud-native.

## Modules

- **Inventory** - Stock tracking, SKU management, warehouses, stock alerts
- **Sales** - Quotes, orders, invoices, customer management, CRM
- **Purchasing** - Purchase orders, vendor management, receiving
- **Accounting** - GL, AP/AR, bank reconciliation, financial reports
- **HR** - Employees, payroll, time tracking, leave management

## Tech Stack

- **Frontend:** Next.js 14+ (App Router), TypeScript, Tailwind CSS, shadcn/ui
- **Backend:** Node.js, Express or tRPC, Prisma ORM
- **Database:** PostgreSQL
- **Auth:** NextAuth.js or Clerk
- **Deployment:** Vercel (frontend), Railway (backend + DB)

## Getting Started

```bash
# Clone
git clone https://github.com/alde1022/startup-erp.git
cd startup-erp

# Install
npm install

# Setup DB
cp .env.example .env
npx prisma migrate dev

# Run
npm run dev
```

## Project Structure

```
startup-erp/
├── apps/
│   └── web/                 # Next.js frontend
├── packages/
│   ├── db/                  # Prisma schema + client
│   ├── api/                 # tRPC routers or REST endpoints
│   └── ui/                  # Shared UI components
├── docker-compose.yml
└── turbo.json               # Monorepo config
```

## License

MIT
