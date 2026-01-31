# Budget with Tiff

A beginner-friendly guide to installing Claude Code and building your very own personal budget tracker — no coding experience required.

---

## Welcome

Claude Code is a tool that helps you build software by having a conversation. You describe what you want, and Claude writes the code for you. Think of it like having a patient, knowledgeable friend who happens to be a programmer.

In this guide, you'll use Claude Code to build a **personal budget tracker** — a simple app where you can log your expenses, organize them by category, and see where your money is going. By the end, you'll have a working app that runs right in your web browser.

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

## Step 3: Get This Project

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
| `CLAUDE.md` | Instructions that tell Claude Code what to build. You don't need to edit this — it's already set up for you. |

---

## Step 4: Open the Project in Claude Code

1. In the Claude desktop app, make sure you're on the **Code** tab.
2. Click **Select folder** (or the equivalent option to open a project).
3. Navigate to the `budget-with-tiff` folder you extracted in Step 3 and select it.
4. Claude Code will read the `CLAUDE.md` file automatically. This gives Claude all the context it needs to help you build your budget tracker.

You're now ready to start building.

---

## Step 5: Start Building

Now for the fun part. In the text input area at the bottom of Claude Code, type a message to tell Claude what you'd like to do. Here are some prompts to get you started:

**Prompt 1 — Build the app:**

> Help me set up my budget tracker app. Create a simple, clean expense tracker where I can add expenses with an amount, category, and date.

**Prompt 2 — Add more features:**

> Add a feature that shows my total spending broken down by category, with a simple chart.

**Prompt 3 — Customize the look:**

> Make the design more colorful and modern. Use soft, friendly colors.

**Prompt 4 — Add editing:**

> Let me edit or delete expenses after I've added them.

Claude will write the code and show you exactly what it plans to create or change. You'll have the option to **accept** or **reject** each change before it's applied.

**The process is iterative:** ask for something, review what Claude builds, then ask for adjustments. You can go back and forth as many times as you like.

---

## Step 6: View Your App

After Claude creates your files, you'll have an `index.html` file in your project folder. To see your app:

1. Open the `budget-with-tiff` folder on your computer.
2. Find the file called `index.html`.
3. Double-click it — it will open in your default web browser (Chrome, Safari, Edge, Firefox, etc.).

That's it. Your budget tracker is now running in your browser. Every time Claude makes changes and you accept them, just refresh the browser page to see the updates.

---

## Tips for Talking to Claude

- **Be specific.** Instead of "make it better," try "make the font bigger and add more space between the expense items."
- **It's okay to say no.** If Claude builds something you don't like, say "that's not what I meant" or "undo that" and try explaining it differently.
- **Ask questions.** If you're curious about how something works, ask Claude to explain it in simple terms.
- **Think out loud.** You can describe what you want in plain language — "I want a dropdown menu where I pick a category like food, rent, or entertainment."
- **Build one piece at a time.** Start simple and add features gradually. You don't need to describe the whole app upfront.

---

## Troubleshooting

**Claude Code doesn't show the Code tab:**
- Make sure you're signed in and have a paid plan (Pro or Max).
- Try closing and reopening the app.

**The app won't open my folder:**
- Make sure you're selecting the folder itself, not a file inside it.
- On Mac, if you see a security warning, go to **System Settings > Privacy & Security** and allow Claude.

**I don't see `index.html` after Claude built the app:**
- Check that you accepted Claude's changes (look for the accept/approve button).
- Look inside the `budget-with-tiff` folder — the file should be right there.

**The app looks broken in my browser:**
- Try a different browser (Chrome usually works best).
- Make sure you're opening the latest version of the file (refresh with `Ctrl+R` or `Cmd+R`).

**I'm stuck or confused:**
- Ask Claude. Seriously — type "I'm stuck, can you help me figure out what to do next?" and Claude will walk you through it.

---

## What's Next

Once your budget tracker is up and running, here are some ideas to keep going:

- **Customize categories:** Add your own spending categories (groceries, subscriptions, coffee, etc.)
- **Add income tracking:** Track money coming in, not just going out.
- **Monthly summaries:** Ask Claude to add a view that shows spending by month.
- **Export to CSV:** Save your data as a spreadsheet file.
- **Dark mode:** Ask Claude to add a dark color theme.

You can also try entirely new projects:

- A to-do list app
- A recipe organizer
- A reading log or book tracker
- A simple journal or diary

**Helpful links:**

- [Claude Code documentation](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Claude pricing and plans](https://claude.ai/pricing)
