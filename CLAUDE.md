## About the User

- Tiffany is a beginner with little to no coding experience.
- She is learning to build software with Claude Code's help.
- When she asks questions, explain concepts in plain, simple language. Avoid jargon.
- Be patient, encouraging, and clear.
- She may not know what terms like "environment variable," "API key," or "database" mean — explain them naturally as they come up.

## Project: Personal Budget Tracker

This project uses an existing open-source budget tracker as a starting template, then customizes it to Tiffany's preferences. The goal is to get Tiffany a fully working, personalized full-stack budget app with minimal friction.

### Template Repository

- **Source:** `https://github.com/chiragyadav2003/Budget-Tracker.git`
- **Stack:** Next.js 14, TypeScript, Tailwind CSS, Shadcn UI, Prisma ORM, PostgreSQL, Clerk Auth, Recharts
- **Features out of the box:** User authentication, expense/income tracking, category management, transaction history with filtering/sorting, monthly/yearly charts, CSV export, dark/light theme, responsive design

## Setup Workflow

When Tiffany asks to set up her budget tracker (or says something like "let's get started," "help me build my app," etc.), follow this exact workflow:

### Phase 1: Clone the Template

1. Clone the template repo into the current project directory:

   ```
   git clone https://github.com/chiragyadav2003/Budget-Tracker.git .
   ```

   If the directory isn't empty (README.md, CLAUDE.md, .gitignore already exist), clone into a temp directory and move the files, preserving the existing CLAUDE.md and README.md.
2. Install dependencies with `npm install`.
3. Briefly tell Tiffany what just happened in plain language: "I just downloaded the starter code for your budget tracker and installed everything it needs to run."

### Phase 2: Analyze the Codebase

Before making any changes, read and understand the full codebase structure. Key files to analyze:

- `app/layout.tsx` — root layout, app metadata, Clerk provider
- `app/globals.css` — CSS variables (color theme)
- `tailwind.config.ts` — Tailwind theme configuration
- `components.json` — Shadcn UI config (base color)
- `components/Logo.tsx` — app logo/branding
- `components/Navbar.tsx` — navigation bar
- `lib/currencies.ts` — supported currencies
- `lib/constants.ts` — app constants (date range limits, etc.)
- `prisma/schema.prisma` — database schema
- `middleware.ts` — auth middleware
- `.env` or `.env.local` — environment variables (will need to be created)

### Phase 3: Enter Plan Mode and Ask Tiffany Questions

After analyzing the codebase, enter plan mode. Present Tiffany with a personalization questionnaire. Ask these questions conversationally (not all at once — group them logically):

**Group 1 — Branding and Identity:**

- What do you want to call your app? (default: "Budget with Tiff")
- Do you prefer a light theme, dark theme, or automatic (matches your device)?

**Group 2 — Colors and Style:**
Show her the current color scheme and ask:

- Pick a vibe: soft pastels, bold and vibrant, minimal and clean, or warm and cozy?
- Any favorite colors she'd like as the primary accent? (e.g., purple, teal, coral, blue)
- Does she want income shown in green and expenses in red, or different colors?

**Group 3 — Currency and Locale:**

- What currency does she use? (The app supports USD, EUR, GBP, JPY, INR — offer to add others if needed)

**Group 4 — Default Categories:**

- What spending categories does she want to start with? Suggest common ones:
  - Rent/Housing, Groceries, Dining Out, Transportation, Utilities, Entertainment, Shopping, Health, Subscriptions, Savings
- What income categories? Suggest: Salary, Freelance, Gifts, Other
- She can always add/remove categories later in the app.

**Group 5 — Services Setup:**
Explain each service simply, then walk her through setup:

- **Database:** She needs a free PostgreSQL database. Recommend Neon (neon.tech) — it's free, no credit card required, and takes 2 minutes to set up. Walk her through creating an account and getting the connection string.
- **Authentication:** She needs a free Clerk account (clerk.com) for login functionality. Walk her through creating a project and getting the API keys.

After collecting her answers, present a clear plan of all the changes you'll make and ask her to approve it.

### Phase 4: Execute the Customizations

Once Tiffany approves the plan, make all the changes:

**Branding:**

- Update the app title in `app/layout.tsx` metadata (title and description)
- Update the logo text in `components/Logo.tsx`
- Update any hardcoded "Budget Tracker" strings throughout the app

**Theme and Colors:**

- Update CSS variables in `app/globals.css` for both light and dark modes
- Update the base color in `components.json` if needed
- Update income/expense color classes in dashboard components (`_components/StatsCards.tsx`, `_components/CategoriesStats.tsx`, `_components/Overview.tsx`)
- If she picked light mode as default, update the root HTML class in `app/layout.tsx`

**Currency:**

- If her currency is already in the list, no changes needed (she picks it in the wizard).
- If she wants a currency not in the list, add it to `lib/currencies.ts`.

**Environment Variables:**

- Create a `.env.local` file with the database and Clerk credentials she provides:

  ```
  POSTGRES_PRISMA_URL=<her-neon-connection-string>
  POSTGRES_URL_NON_POOLING=<her-neon-direct-connection-string>
  NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=<her-clerk-publishable-key>
  CLERK_SECRET_KEY=<her-clerk-secret-key>
  ```

**Database:**

- Run `npx prisma generate` to generate the Prisma client.
- Run `npx prisma db push` to create the database tables.

**Launch:**

- Run `npm run dev` to start the development server.
- Tell Tiffany to open `http://localhost:3000` in her browser.
- Walk her through the setup wizard (currency selection) that appears on first login.
- Once she confirms the app is working locally, ask if she'd like to put it on the internet so she can access it from anywhere (proceed to Phase 5).

### Phase 5: Deploy to Vercel

This template is built for Vercel. Vercel is a free hosting service that puts the app on the internet with a real URL she can access from any device. Only proceed with this phase after the app is working locally and Tiffany confirms she wants to deploy.

**Step 1 — Install the Vercel CLI:**

Run `npm install -g vercel`. Explain to Tiffany: "This installs a small tool that uploads your app to the internet."

**Step 2 — Log in to Vercel:**

Run `vercel login`. This will open a browser window for Tiffany to create a free Vercel account (or sign in if she has one). Walk her through it:
- She can sign up with her email, GitHub, or Google account.
- The free Hobby plan is all she needs — no credit card required.
- After signing in, the terminal will confirm she's logged in.

**Step 3 — Deploy:**

Run `vercel` from the project root. Walk Tiffany through the interactive prompts:
- **Set up and deploy?** Yes
- **Which scope?** Her account (the only option for a new account)
- **Link to existing project?** No — create a new one
- **Project name?** Use her app name (e.g., "budget-with-tiff")
- **Directory with your code?** `.` (current directory, the default)
- **Override settings?** No (the defaults are correct for Next.js)

Vercel will build and deploy the app. It will output a preview URL.

**Step 4 — Set environment variables on Vercel:**

The deployed app needs the same environment variables as local. Run these commands (using the values from her `.env.local`):

```
vercel env add POSTGRES_PRISMA_URL production
vercel env add POSTGRES_URL_NON_POOLING production
vercel env add NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY production
vercel env add CLERK_SECRET_KEY production
```

Each command will prompt for the value. Walk Tiffany through pasting each one. Explain: "These are the same connection codes we set up earlier — we're just telling the live version of your app how to find your database and login service."

**Step 5 — Deploy to production:**

Run `vercel --prod` to push a production deployment with the environment variables active.

**Step 6 — Update Clerk:**

The deployed app will have a new URL (e.g., `budget-with-tiff.vercel.app`). Walk Tiffany through adding this URL to her Clerk project's allowed origins:
1. Go to clerk.com and open her project dashboard.
2. Navigate to **Domains** or **Allowed origins** in settings.
3. Add the Vercel production URL.

**Step 7 — Celebrate:**

Give Tiffany her live URL and explain:
- She can open this URL from any device — phone, tablet, another computer.
- She can share the URL with anyone she wants to use the app (they'll create their own login).
- Any future changes she makes locally can be re-deployed by running `vercel --prod` again.

**Re-deploying after changes:**

If Tiffany makes changes later and wants to update the live app, just run `vercel --prod` again. Explain that it's like saving a new version to the internet.

## Key Customization Reference

These are the files and values most likely to change based on Tiffany's preferences:

| What to change | Where |
|---------------|-------|
| App name / page title | `app/layout.tsx` (metadata object) |
| Logo text | `components/Logo.tsx` |
| Color theme (light) | `app/globals.css` (`:root` block) |
| Color theme (dark) | `app/globals.css` (`.dark` block) |
| Default theme mode | `app/layout.tsx` (html className) |
| Shadcn base color | `components.json` (baseColor) |
| Supported currencies | `lib/currencies.ts` |
| Max date range | `lib/constants.ts` (MAX_DATE_RANGE_DAYS) |
| Income color | Components using `emerald` classes |
| Expense color | Components using `rose` classes |
| Auth config | `middleware.ts`, `.env.local` |
| Database schema | `prisma/schema.prisma` |

## Changelog

This project uses a `CHANGELOG.md` file to track every change made to the app. This is important because Tiffany may come back across multiple sessions, and the changelog gives both her and Claude a clear history of what's been done.

### Rules

- The changelog file lives at the project root: `CHANGELOG.md`
- Create the file during Phase 4 (after the initial customizations) with the first set of entries.
- **After every change you make to the project, update the changelog.** This includes setup steps, customizations, feature additions, bug fixes, style changes, and deployments.
- Use plain, non-technical language that Tiffany can understand. She should be able to read the changelog and know exactly what changed.
- **At the start of every new session**, read `CHANGELOG.md` first to understand what has already been done. This prevents re-doing work or asking questions that have already been answered.

### Format

Use this format. Group entries by date. Newest entries go at the top.

```markdown
# Changelog

All changes to your budget tracker are listed here, newest first.

## Jan 31, 2026

### Setup
- Downloaded the budget tracker starter code
- Set up the database connection (Neon)
- Set up login (Clerk)
- Ran the app for the first time

### Customization
- Changed the app name to "Tiff's Budget"
- Updated colors to a soft pastel theme (lavender accent)
- Set default currency to USD
- Added spending categories: Groceries, Rent, Dining Out, Coffee, Subscriptions

### Deployment
- Deployed the app to Vercel
- Live at: https://budget-with-tiff.vercel.app
```

### What to log

| Type | Example entry |
|------|--------------|
| Setup | "Set up the database connection (Neon)" |
| Customization | "Changed the accent color from purple to teal" |
| Feature | "Added a monthly budget limit feature" |
| Fix | "Fixed the chart not showing up on the dashboard" |
| Style | "Made the buttons bigger and easier to tap on mobile" |
| Deployment | "Re-deployed to Vercel with the latest changes" |

### Session startup

When starting a new conversation with Tiffany:

1. Read `CHANGELOG.md` to understand the current state of the project.
2. Briefly greet Tiffany and recap what was done last time based on the changelog. For example: "Last time we set up your app and deployed it. You've got categories for Groceries, Rent, and Coffee. What would you like to work on today?"
3. This recap helps Tiffany remember where she left off without having to explain everything again.

## Behavior Guidelines

- Walk Tiffany through every step. Don't assume she knows how to do anything.
- When setting up external services (Neon, Clerk), give her step-by-step instructions she can follow in her browser. Tell her exactly what to click and where to copy values from.
- If something goes wrong (build error, database connection issue, etc.), explain what happened in plain language and fix it.
- After the app is running, suggest small customizations she can ask for: "Want me to change the colors?" "Should we add a category for soda?"
- Keep her excited and confident. Celebrate milestones: "Your app is live!" "You just added your first feature!"
- Never dump walls of technical output at her. Summarize what happened and whether it worked.
