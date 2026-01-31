# Budget with Tiff

A beginner-friendly guide to installing Claude Code and setting up your very own personal budget tracker — no coding experience required.

---

## Welcome

Claude Code is a tool that helps you build software by having a conversation. You describe what you want, and Claude writes the code for you. Think of it like having a patient, knowledgeable friend who happens to be a programmer.

In this guide, you'll use Claude Code to set up a **personal budget tracker** — a real app with user login, expense tracking, charts, and more. Claude will walk you through every step, ask you some questions about your preferences (colors, categories, currency), and customize the app to fit your style.

**All you need is:**

- A computer (Mac or Windows)
- An internet connection
- A Claude account (we'll set that up below)

---

## Step 1: Create Your Claude Account

Before you can use Claude Code, you need a Claude account with a paid plan.

1. Go to [claude.ai](https://claude.ai) in your web browser.
2. Click **Sign Up** and create an account using your email (or sign in with Google/Apple).
3. Subscribe to a **Claude Pro** or **Claude Max** plan.
   - Claude Code is included with your paid subscription — no separate API key or extra setup needed.
   - You can view plan options at [claude.ai/pricing](https://claude.ai/pricing).

Once you're signed up and subscribed, you're ready to install the app.

---

## Step 2: Install Claude Code

### On Mac

1. Download the Claude desktop app from [claude.ai/download](https://claude.ai/download).
2. Open the downloaded `.dmg` file.
3. Drag **Claude** into your **Applications** folder.
4. Open Claude from your Applications folder (or search for "Claude" using Spotlight with `Cmd + Space`).
5. Sign in with the account you created in Step 1.

### On Windows

1. Download the Claude desktop app from [claude.ai/download](https://claude.ai/download).
2. Run the installer (`.exe` file) and follow the on-screen prompts.
3. Once installed, open Claude from the Start menu (search for "Claude").
4. Sign in with the account you created in Step 1.

After signing in, look for the **Code** tab in the top left of the app window and click it. If prompted to complete sign-in, follow the instructions and restart the app.

---

## Step 3: Install Node.js

Your budget tracker needs Node.js to run. Node.js is a program that runs the code behind your app — you install it once and don't need to think about it again.

### On Mac

1. Go to [nodejs.org](https://nodejs.org).
2. Click the **LTS** (Long Term Support) download button — it's the one on the left.
3. Open the downloaded `.pkg` file and follow the installer steps.
4. To confirm it worked, open **Terminal** (search for "Terminal" using Spotlight with `Cmd + Space`) and type:
   ```
   node --version
   ```
   You should see a version number like `v22.x.x`. If you do, you're good.

### On Windows

1. Go to [nodejs.org](https://nodejs.org).
2. Click the **LTS** download button.
3. Run the installer (`.msi` file) and follow the prompts. Leave all the default options checked.
4. To confirm it worked, open **Command Prompt** (search for "cmd" in the Start menu) and type:
   ```
   node --version
   ```
   You should see a version number. If you do, you're all set.

---

## Step 4: Get This Project

You don't need Git or any developer tools. Here's how to download this project as a ZIP file:

1. Go to this project's GitHub page (the page you're reading this on).
2. Click the green **Code** button near the top of the page.
3. Select **Download ZIP** from the dropdown menu.
4. Find the downloaded ZIP file (usually in your **Downloads** folder).
5. **Extract/unzip it:**
   - **Mac:** Double-click the ZIP file. A folder will appear next to it.
   - **Windows:** Right-click the ZIP file and select **Extract All**, then click **Extract**.
6. Move the extracted folder somewhere easy to find, like your **Desktop** or **Documents** folder.

**What's inside the folder:**

| File | What it does |
|------|-------------|
| `README.md` | This guide you're reading right now. |
| `CLAUDE.md` | Instructions that tell Claude Code what to build and how to customize it for you. You don't need to edit this. |

---

## Step 5: Open the Project in Claude Code

1. In the Claude desktop app, make sure you're on the **Code** tab.
2. Click **Select folder** (or the equivalent option to open a project).
3. Navigate to the `budget-with-tiff` folder you extracted in Step 4 and select it.
4. Claude Code will read the `CLAUDE.md` file automatically. This gives Claude all the context it needs to set up and customize your budget tracker.

You're now ready to start.

---

## Step 6: Start Building

Type one of these messages to Claude to kick things off:

> Help me set up my budget tracker.

or simply:

> Let's get started!

### What happens next

Claude will:

1. **Download the starter code** — a pre-built budget tracker template with all the features you need.
2. **Ask you some questions** — Claude will ask about your preferences:
   - What do you want to call your app?
   - What colors do you like?
   - What currency do you use?
   - What spending categories do you want (groceries, rent, entertainment, etc.)?
3. **Walk you through creating one free account** — a Supabase account that handles both your database (where your data is stored) and your login (so your data is private and secure). Claude will tell you exactly what to click.
4. **Customize everything** — Claude applies your choices: colors, name, categories, and more.
5. **Launch your app** — Claude starts the app and tells you where to open it in your browser.
6. **Put it on the internet** — Once the app is working on your computer, Claude will offer to deploy it so you can access it from any device with a real web address.

You'll see your app at `http://localhost:3000` in your web browser.

---

## Step 7: Use Your App

Once the app is running:

1. **Sign up** — Create an account using the login screen (this is your personal app login, separate from your Claude account).
2. **Pick your currency** — The setup wizard will ask you to choose.
3. **Start tracking** — Add your first expense or income entry.

### What you can do in the app

- Add expenses and income with amounts, categories, and dates
- See your spending broken down by category with charts
- View your full transaction history
- Filter and sort transactions
- Export your data to a spreadsheet (CSV)
- Switch between light and dark mode
- Manage your categories (add new ones, remove old ones)

---

## Step 8: Put Your App on the Internet (Optional)

Once your app is working on your computer, you can put it on the internet so you can access it from your phone, another computer, or share it with others.

When you're ready, just tell Claude:

> I want to put my app on the internet.

or:

> Help me deploy my app.

Claude will walk you through setting up a free account on **Vercel** (a hosting service) and uploading your app. At the end, you'll get a real web address like `budget-with-tiff.vercel.app` that works from any device.

- The Vercel free plan is all you need — no credit card required.
- Your data stays in the same database, whether you use the app locally or from the internet.
- If you make changes later, you can re-deploy with one command and Claude will show you how.

---

## Tips for Talking to Claude

- **Be specific.** Instead of "make it better," try "make the header color blue" or "add a category for coffee shops."
- **It's okay to say no.** If Claude builds something you don't like, say "that's not what I meant" and try explaining it differently.
- **Ask questions.** If you're curious about how something works, ask Claude to explain it simply.
- **Think out loud.** Describe what you want in plain language — "I want a section that shows how much I spent this month."
- **Ask for changes anytime.** You can always ask Claude to change colors, add features, or rearrange things.

---

## Troubleshooting

**Claude Code doesn't show the Code tab:**
- Make sure you're signed in and have a paid plan (Pro or Max).
- Try closing and reopening the app.

**"node" is not recognized or command not found:**
- Node.js might not be installed. Go back to Step 3 and install it.
- On Windows, try closing and reopening Command Prompt after installing Node.js.

**The app won't open my folder:**
- Make sure you're selecting the folder itself, not a file inside it.
- On Mac, if you see a security warning, go to **System Settings > Privacy & Security** and allow Claude.

**The app won't start or shows errors:**
- Ask Claude. Type "the app isn't starting, can you help?" and Claude will diagnose the problem.
- Make sure you completed the Supabase setup when Claude asked (database and login are both handled there).

**I see a blank page at localhost:3000:**
- Try refreshing the page.
- Check if Claude is still setting things up — wait for Claude to say the app is ready.

**The deployed app shows errors or a blank page:**
- Make sure the environment variables were added to Vercel (Claude will have walked you through this).
- Make sure the Vercel URL was added to your Supabase project's redirect URLs.
- Ask Claude: "My deployed app isn't working, can you help me debug it?"

**I'm stuck or confused:**
- Type "I'm stuck, can you help me figure out what to do next?" — Claude will walk you through it.

---

## What's Next

Once your budget tracker is up and running, here are some things you can ask Claude to do:

- **New categories:** "Add a category for coffee shops with a coffee emoji."
- **Change the look:** "Make the app more colorful" or "Switch to a purple theme."
- **Monthly goals:** "Add a feature where I can set a monthly budget limit."
- **Recurring expenses:** "Let me mark some expenses as recurring so I don't have to re-enter them."
- **Charts:** "Show me a bar chart of my spending over the last 6 months."

You can also try building entirely new projects:

- A to-do list app
- A recipe organizer
- A reading log or book tracker
- A simple journal or diary

**Helpful links:**

- [Claude Code documentation](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Claude pricing and plans](https://claude.ai/pricing)
