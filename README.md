# II.0 - Relationship Operating System

A new structure for modern relationships. Built on clarity, trust, and mutual respect.

## Overview

II.0 introduces structure where ambiguity used to exist, clarity where manipulation used to thrive, and dignity where stigma used to live.

## Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Database**: Supabase (PostgreSQL)
- **Authentication**: Supabase Auth (Magic Links)
- **Payments**: Stripe Connect (Escrow)
- **Video**: Daily.co (WebRTC)
- **AI**: Anthropic Claude API
- **Styling**: Tailwind CSS

## Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn
- Supabase account
- Stripe account
- Daily.co account
- Anthropic API key

### Installation

1. Clone the repository:
```bash
cd ii0-app
```

2. Install dependencies:
```bash
npm install
```

3. Copy the environment file:
```bash
cp .env.local.example .env.local
```

4. Fill in your environment variables in `.env.local`:
```
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key

STRIPE_SECRET_KEY=sk_test_xxx
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=pk_test_xxx
STRIPE_WEBHOOK_SECRET=whsec_xxx

DAILY_API_KEY=your_daily_api_key

ANTHROPIC_API_KEY=your_anthropic_api_key

NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### Database Setup

1. Go to your Supabase project's SQL Editor
2. Run the schema from `supabase/schema.sql`

### Stripe Setup

1. Create a Stripe account
2. Enable Stripe Connect
3. Set up the webhook endpoint: `your-domain.com/api/stripe/webhook`
4. Add events: `payment_intent.amount_capturable_updated`, `payment_intent.succeeded`, `payment_intent.payment_failed`, `charge.refunded`, `account.updated`

### Daily.co Setup

1. Create a Daily.co account
2. Get your API key from the dashboard

### Running the App

```bash
npm run dev
```

Visit `http://localhost:3000`

## User Flows

### Lifestyle Creator
1. Sign up with email (magic link)
2. Select "Build my lifestyle" role
3. Complete profile setup
4. Upload photos/videos
5. Create lifestyle goals
6. Receive support from providers
7. Engage in structured conversations

### Provider
1. Sign up with email (magic link)
2. Select "Support a lifestyle" role
3. Complete profile setup
4. Discover creators
5. View profiles and goals
6. Fund goals (escrow)
7. Unlock conversations
8. Engage in structured interactions

## Features

- **Magic Link Authentication**: No passwords required
- **Goal-Based Support**: Clear, fundable objectives
- **Escrow System**: Funds held securely
- **Real-Time Messaging**: Instant communication
- **Voice Messages**: Available after threshold
- **Video Calls**: Timed sessions with auto-end
- **AI Integration**:
  - II.0 Guide: Platform assistance
  - Lifestyle Architect: Goal creation help
  - Relationship Integrity Monitor: Safety monitoring

## Architecture

```
app/
├── (auth)/          # Authentication pages
├── onboarding/      # User onboarding flow
├── discover/        # Provider discovery
├── profile/         # Profile viewing/editing
├── fund/            # Funding flow
├── messages/        # Messaging system
├── video/           # Video calling
├── dashboard/       # Creator dashboard
├── admin/           # Admin panel
└── api/             # API routes
```

## Design Philosophy

Every decision must answer one question:

> "Does this increase clarity, trust, and dignity for both sides?"

If the answer is no, do not build it.

## License

Proprietary - All rights reserved
# twopointzero
