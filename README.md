# Squirell

**Gather Small. Grow Big.**

Squirell is a family-first fintech application concept designed to help
parents and teens build healthier saving habits together. It brings
family savings, goal tracking, financial requests, and money education
into one approachable experience.

> **Project status:** Early-stage application foundation / development
> project. Financial activity in the initial version is simulated.
> Squirell does not process real payments, UPI transfers, deposits, or
> banking transactions.

## Product vision

Make saving a shared family habit and help young people develop
confidence with money through practical, goal-based experiences.

## Experiences

### Parent

-   View a family savings dashboard.
-   Add and manage teen profiles.
-   Track each teen's savings and goals.
-   Create and manage family or individual savings goals.
-   Review simulated financial requests and approve or reject them.
-   Configure demo RoundUp settings.
-   Review family transaction activity.
-   View and manage simulated virtual cards.

### Teen

-   View a personal savings dashboard.
-   Track savings balance and goal progress.
-   Make flexible demo contributions.
-   Explore a RoundUp savings calculator.
-   Use a simulated UPI payment flow.
-   Review transaction history.
-   View a simulated virtual card.
-   Earn and track achievements and milestones.

## Core principles

-   **Family-first:** Parents and teens have distinct, role-appropriate
    experiences.
-   **Habit-building:** Make progress visible through goals, milestones,
    and small contributions.
-   **Learning by doing:** Help teens understand everyday money
    decisions.
-   **Transparency:** Clearly label simulated balances, cards, payments,
    and transactions.
-   **Privacy and safety:** Protect personal data and apply role-based
    access controls.

## Technology

The planned application foundation uses:

-   **React** for the user interface.
-   **TypeScript** for typed application code.
-   **Responsive, mobile-first UI** to support desktop and mobile
    screens.
-   **Supabase** for authentication and persistent database storage when
    configured.
-   **Mock data and simulated transactions** for development and demos.

The project should remain structured so that native Android and iOS
applications can be considered in a future phase. No paid API or payment
provider is required for the initial demo.

## Getting started

### Prerequisites

Install:

-   [Node.js](https://nodejs.org/) (LTS recommended)
-   npm (included with Node.js)
-   Git (optional, for version control)

### Install dependencies

From the project root, run:

``` bash
npm install
```

### Start the development server

``` bash
npm run dev
```

Open the local URL printed in the terminal (Vite commonly uses
`http://localhost:5173`).

### Create a production build

``` bash
npm run build
```

### Preview the production build locally

``` bash
npm run preview
```

> These commands assume the project is configured with Vite and the
> corresponding npm scripts. If the repository uses a different build
> tool, follow the scripts in its `package.json`.

## Environment configuration

The application should work in demo mode without Supabase credentials.
To enable Supabase, create a project and add the public project URL and
publishable/anonymous key to a local environment file.

Example `.env.local`:

``` env
VITE_SUPABASE_URL=https://YOUR_PROJECT.supabase.co
VITE_SUPABASE_ANON_KEY=YOUR_SUPABASE_PUBLISHABLE_OR_ANON_KEY
```

Do not commit `.env.local` or any secret keys. Add local environment
files to `.gitignore`.

Only public client-side Supabase credentials belong in the frontend.
Never expose a Supabase service-role key, database password, or other
privileged secret in browser code.

## Suggested project structure

The exact structure may evolve as implementation progresses. A
maintainable starting point could look like:

``` text
squirell/
├── public/
│   └── assets/
├── src/
│   ├── app/
│   │   ├── routes/
│   │   └── providers/
│   ├── components/
│   │   ├── ui/
│   │   └── layout/
│   ├── features/
│   │   ├── auth/
│   │   ├── parent/
│   │   ├── teen/
│   │   ├── savings/
│   │   ├── goals/
│   │   ├── requests/
│   │   ├── roundup/
│   │   ├── cards/
│   │   └── activity/
│   ├── lib/
│   │   └── supabase/
│   ├── data/
│   ├── hooks/
│   ├── types/
│   └── styles/
├── .env.example
├── .gitignore
├── package.json
├── tsconfig.json
└── README.md
```

## Data and access model

When Supabase is configured:

-   Authenticate users through Supabase Auth.
-   Associate teen profiles with the appropriate family and parent
    account.
-   Enforce permissions in the database with Row Level Security (RLS),
    not only by hiding UI controls.
-   Ensure parents can access only the family information they are
    authorised to manage.
-   Ensure teens can access only their own permitted profile, savings,
    goals, and activity.
-   Validate all inputs and enforce authorisation on every data-changing
    operation.

For local development without Supabase, use clearly identified mock
data. Do not treat mock authentication or frontend-only role switching
as production security.

## Demo activity and financial safety

The initial application is a product demonstration and financial
education experience.

-   No real bank accounts are connected.
-   No real money is deposited, withdrawn, transferred, or stored.
-   UPI interactions are simulated and do not send payments.
-   Virtual cards are visual/demo interfaces and cannot be used to
    transact.
-   RoundUp calculations are illustrative only.
-   Demo balances and transaction histories are not real financial
    records.

Any future real-money functionality would require deliberate product,
legal, compliance, security, and regulated-partner decisions before
implementation.

## Design direction

Squirell's visual identity is based on:

-   **Squirell red** for primary actions and brand emphasis.
-   **White and warm off-white** surfaces.
-   **Black / espresso** typography.
-   Soft cream secondary surfaces.
-   Rounded components, clear hierarchy, and refined spacing.
-   Subtle motion and useful feedback.
-   Legible charts and savings progress indicators.

The interface should feel premium, friendly, and trustworthy without
relying on cartoon illustrations or generic banking templates.

## Development priorities

1.  Establish the application foundation and responsive navigation.
2.  Build onboarding and distinct Parent / Teen entry experiences.
3.  Implement functional Parent and Teen dashboards.
4.  Add profiles, savings goals, contributions, and simulated requests.
5.  Add RoundUp calculator, demo UPI flow, virtual cards, and activity
    history.
6.  Add achievements, empty states, loading states, and error handling.
7.  Configure Supabase authentication, schema, and RLS when the backend
    is ready.
8.  Test role permissions, responsive layouts, accessibility, and
    production builds.

## Contributing

Squirell is an evolving product project. Keep changes focused, use
TypeScript types, prefer reusable components, and document any new
environment variables or setup steps. Never commit credentials, real
personal financial data, or secrets.

## Brand

**Squirell --- Gather Small. Grow Big.**

