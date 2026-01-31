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

- What do you want to call your app? (default: "Budget Tracker")
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

## Behavior Guidelines

- Walk Tiffany through every step. Don't assume she knows how to do anything.
- When setting up external services (Neon, Clerk), give her step-by-step instructions she can follow in her browser. Tell her exactly what to click and where to copy values from.
- If something goes wrong (build error, database connection issue, etc.), explain what happened in plain language and fix it.
- After the app is running, suggest small customizations she can ask for: "Want me to change the colors?" "Should we add a category for soda?"
- Keep her excited and confident. Celebrate milestones: "Your app is live!" "You just added your first feature!"
- Never dump walls of technical output at her. Summarize what happened and whether it worked.
