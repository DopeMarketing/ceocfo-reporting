# CEO/CFO Reporting Platform — Claude Development Brief

## Project Overview
A personal financial reporting platform that automates CEO/CFO-level analysis by integrating QuickBooks, Stripe, Shopify, and other financial tools. Generates automated P&L reports, reconciles transactions, forecasts cash flow, and provides AI-powered financial insights.

## Tech Stack
- **Frontend:** Next.js 15 (App Router), TypeScript, Tailwind CSS
- **Backend:** Supabase (PostgreSQL, RLS, Auth)
- **Integrations:** QuickBooks, Stripe, Shopify, Google Sheets, Gmail
- **Automation:** Zapier, Make, Pipedream webhooks
- **Deployment:** Vercel
- **AI:** OpenAI for insights and analysis

## Folder Structure

app/
  (auth)/           # Auth pages (login, etc.)
  dashboard/        # Main dashboard page
  reports/          # P&L, variance, templates
  reconciliation/   # Transaction matching
  forecasting/      # Cash flow forecasts
  insights/         # AI-powered insights
  google-sheets/    # Sheets integration
  expense-automation/ # Email receipt processing
  integrations/     # Integration setup pages
  globals.css       # Global styles
  layout.tsx        # Root layout
  page.tsx          # Homepage

components/
  ui/               # Reusable UI components
  dashboard/        # Dashboard-specific components
  reports/          # Report components
  integrations/     # Integration components

lib/
  utils.ts          # General utilities
  auth.ts           # Auth helpers
  validations.ts    # Zod schemas
  constants.ts      # App constants

db/
  queries.ts        # Database queries
  types.ts          # Database types
  client.ts         # Supabase client

actions/
  auth.ts           # Auth server actions
  reports.ts        # Report generation
  reconciliation.ts # Transaction matching
  integrations.ts   # Integration management

integrations/
  quickbooks/       # QuickBooks API client
  stripe/           # Stripe API client
  shopify/          # Shopify API client
  google-sheets/    # Google Sheets API
  gmail/            # Gmail API client

supabase/
  migrations/       # Database migrations
  config.toml       # Supabase config


## Coding Conventions
- **TypeScript:** Strict mode enabled, no `any` types
- **Components:** Server components by default, use 'use client' only when necessary
- **Data Access:** Only in `/db` folder, never in components
- **Business Logic:** Only in `/lib` and `/actions`
- **Secrets:** Never in client components, use server actions
- **Styling:** Tailwind CSS with consistent spacing scale
- **File Naming:** kebab-case for files, PascalCase for components

## Current State: Scaffold
This is a fresh scaffold with:
- ✅ Complete database schema (14 tables)
- ✅ Route structure (18 pages)
- ✅ Integration stubs for all platforms
- ✅ Basic authentication setup
- ✅ Supabase configuration
- ❌ No features implemented yet
- ❌ UI components are placeholders
- ❌ Integration APIs not connected

## What to Build Next: v1 Features

### Priority Order:
1. **Automated monthly P&L report generation** — QuickBooks data → executive PDF reports
2. **Executive summary dashboard builder** — Key metrics in Google Sheets templates
3. **Real-time Stripe transaction reconciliation** — Match payments to QuickBooks invoices
4. **Cash flow forecasting dashboard** — 90-day projections from all data sources
5. **AI-powered financial insights engine** — Trend analysis and anomaly detection
6. **Budget vs actuals variance analysis** — Automated deviation flagging

## Never Touch Rules
- **Environment files:** Never modify .env files without explicit instruction
- **Migrations:** Never edit existing migration files, only create new ones
- **RLS Policies:** Never modify Row Level Security without security review
- **Production config:** Never change Vercel or Supabase production settings

## How to Work on This Project

### Before Starting Any Session:
1. **Always read this file first** to understand current state
2. Ask about specific feature to implement
3. Review relevant database tables and API endpoints

### During Development:
1. **Start small:** Build one component or feature at a time
2. **Test frequently:** Run `npm run dev` to verify changes
3. **Follow data flow:** DB → Server Action → Component
4. **Handle errors:** Use try/catch and user-friendly error messages

### Before Finishing:
1. **Build check:** Run `npm run build` to verify no TypeScript errors
2. **Commit properly:** Use conventional commit messages
3. **Document debt:** Add any shortcuts to TECHNICAL_DEBT.md
4. **Update progress:** Note what was completed

### Integration Development Priority:
1. QuickBooks (core financial data)
2. Stripe (payment reconciliation)
3. Google Sheets (reporting output)
4. Shopify (sales forecasting)
5. Gmail (expense automation)

### Database Schema Notes:
- `users` and `organizations` for multi-tenancy
- Financial data normalized across `quickbooks_*`, `stripe_*`, `shopify_*`
- `transaction_reconciliations` for matching across platforms
- `reports`, `cash_flow_forecasts` for generated outputs
- `ai_insights` for ML-generated analysis

Remember: This is a personal finance tool, so prioritize accuracy and reliability over flashy features.