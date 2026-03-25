# CEO/CFO Reporting Platform

Automated financial reporting and analysis dashboard that connects QuickBooks, Stripe, Shopify, and other financial tools to generate executive-ready reports and insights.

## What it does

This platform acts as your functional CFO by automating financial data collection, analysis, and reporting across your entire financial stack. It generates monthly P&L reports, reconciles transactions, forecasts cash flow, and provides AI-powered insights to help you make better financial decisions.

**Built for:** Personal use by founders and small business owners who need CFO-level financial analysis without the CFO price tag.

## Tech Stack

- **Frontend:** Next.js 15, TypeScript, Tailwind CSS
- **Backend:** Supabase (PostgreSQL, Auth, RLS)
- **Integrations:** QuickBooks, Stripe, Shopify, Google Sheets, Gmail
- **Automation:** Zapier, Make, Pipedream
- **Deployment:** Vercel
- **AI/ML:** OpenAI for financial insights and analysis

## Prerequisites

- Node.js 18+ and npm
- Supabase CLI
- Git

## Local Setup

1. **Clone the repository**
   bash
   git clone <repository-url>
   cd ceo-cfo-reporting
   

2. **Install dependencies**
   bash
   npm install
   

3. **Set up environment variables**
   bash
   cp .env.example .env.local
   
   Fill in your environment variables (see table below)

4. **Start Supabase**
   bash
   npx supabase start
   

5. **Run the development server**
   bash
   npm run dev
   

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `NEXT_PUBLIC_SUPABASE_URL` | Your Supabase project URL | Yes |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | Your Supabase anonymous key | Yes |
| `SUPABASE_SERVICE_ROLE_KEY` | Service role key for server operations | Yes |
| `QUICKBOOKS_CLIENT_ID` | QuickBooks OAuth client ID | Yes |
| `QUICKBOOKS_CLIENT_SECRET` | QuickBooks OAuth client secret | Yes |
| `STRIPE_SECRET_KEY` | Stripe secret key | Yes |
| `STRIPE_WEBHOOK_SECRET` | Stripe webhook endpoint secret | Yes |
| `SHOPIFY_API_KEY` | Shopify API key | Yes |
| `SHOPIFY_API_SECRET` | Shopify API secret | Yes |
| `GOOGLE_CLIENT_ID` | Google OAuth client ID | Yes |
| `GOOGLE_CLIENT_SECRET` | Google OAuth client secret | Yes |
| `OPENAI_API_KEY` | OpenAI API key for AI insights | Yes |
| `GMAIL_CLIENT_ID` | Gmail API client ID | Yes |
| `GMAIL_CLIENT_SECRET` | Gmail API client secret | Yes |
| `ZAPIER_WEBHOOK_URL` | Zapier webhook URL | No |
| `MAKE_WEBHOOK_URL` | Make webhook URL | No |
| `PIPEDREAM_WEBHOOK_URL` | Pipedream webhook URL | No |

## Database Setup

The database schema is automatically applied when you run `supabase start`. The schema includes:

- Users and organizations
- Integration configurations
- Financial data from QuickBooks, Stripe, Shopify
- Transaction reconciliation
- Reports and forecasts
- AI insights and expense categories

## Deploy to Vercel

1. **Connect to Vercel**
   bash
   npx vercel --yes
   

2. **Set environment variables in Vercel dashboard**
   - Go to your project settings
   - Add all environment variables from the table above

3. **Deploy**
   bash
   npx vercel --prod
   

## Project Structure


├── app/                 # Next.js 15 app router
│   ├── (auth)/         # Authentication pages
│   ├── dashboard/      # Main dashboard
│   ├── reports/        # Report pages
│   ├── reconciliation/ # Transaction reconciliation
│   └── integrations/   # Integration setup
├── components/         # React components
├── lib/               # Business logic and utilities
├── db/                # Database queries and types
├── actions/           # Server actions
├── integrations/      # Third-party API clients
├── supabase/          # Database migrations and config
└── public/            # Static assets


## Contributing

This is a personal project scaffold. See CLAUDE.md for development guidelines when working with AI assistance.