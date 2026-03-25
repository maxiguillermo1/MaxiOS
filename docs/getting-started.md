# Getting started with MaxisOS

This guide walks you from zero to a working setup. You do not need a technical background—follow the steps in order.

---

## What you will do (checklist)

Do these once, top to bottom:

1. [ ] Install **Obsidian** and create a vault (a folder for your notes).
2. [ ] Install **Claude Code** and sign in with a **Pro, Max, or Team** plan.
3. [ ] Copy **MaxisOS** into your vault and run the installer script.
4. [ ] Open **Claude Code** with your **vault folder** as the project (this part is easy to get wrong—see Step 4).
5. [ ] In chat, say: **“Initialize my vault”** and answer the setup questions.

After that, you use MaxisOS by **talking to Claude** in plain language.

---

## Before you start: what to download

| You need | What it is | Link |
|----------|------------|------|
| **Obsidian** | Free app where your notes live | [obsidian.md](https://obsidian.md) |
| **Claude Code** | Anthropic’s app that runs MaxisOS inside your vault | [claude.ai/code](https://claude.ai/code) |
| **Paid Claude plan** | Pro, Max, or Team (required for Claude Code) | Same as above |
| **Git** | Lets your computer download MaxisOS from the internet | Mac: often prompted in Terminal; Windows: [git-scm.com](https://git-scm.com) |

**Optional (only if you want email and calendar in your vault):**

- Gmail and Google Calendar, connected when the installer or onboarding asks.

---

## Step 1: Install Obsidian and create a vault

1. Download Obsidian from [obsidian.md](https://obsidian.md) for your computer (Mac, Windows, or Linux).
2. Open Obsidian.
3. Choose **Create new vault** (or open an existing vault if you already use Obsidian).
4. Pick a **name** (for example “Notes” or “Work vault”).
5. Pick a **folder location** on your computer and finish the wizard.
6. **Remember that folder path**—you will use it in Step 3.

### Recommended Obsidian plugins (optional but useful)

These are not required for MaxisOS to run, but they make Obsidian nicer:

1. In Obsidian, open **Settings** (gear icon, bottom left).
2. Open **Community plugins** → turn on **Safe mode** off if asked → **Browse**.
3. Install these when you are ready:

**Start with these four:**

| Plugin | Why |
|--------|-----|
| **Templater** | Smarter note templates |
| **Dataview** | Tables and queries over your notes |
| **Calendar** | Calendar in the sidebar |
| **Tasks** | Tasks with due dates |

**Add later if you like:** QuickAdd, Folder Notes, Tag Wrangler, Periodic Notes, Omnisearch.

During setup, the **Architect** helper may remind you about plugins if something is missing.

---

## Step 2: Install Claude Code

1. Open [claude.ai/code](https://claude.ai/code) and install **Claude Code** for your system.
2. Sign in with an account that has **Claude Pro**, **Max**, or **Team**.
3. You can use **Desktop (Cowork)** or the **terminal** (`claude` command). MaxisOS supports both.

---

## Step 3: Put MaxisOS inside your vault and run the installer

MaxisOS must live **inside** your Obsidian vault folder so helpers can read and write your notes.

### 3a. Open a terminal

- **Mac:** Press `Command + Space`, type `Terminal`, press Enter.
- **Windows:** Press `Windows + R`, type `cmd`, press Enter.

### 3b. Go to your vault folder

Replace the path with **your** vault location (the folder you chose in Step 1):

```bash
cd /path/to/your-vault
```

**Tip:** On Mac, you can type `cd ` (with a space), then drag your vault folder from Finder into the terminal window, then press Enter.

### 3c. Download MaxisOS

```bash
git clone https://github.com/maxiguillermo1/MaxisOS.git
```

That command creates a folder named `MaxisOS` inside your vault (matching the GitHub repo name). The rest of this guide assumes that folder name. Official repo: [github.com/maxiguillermo1/MaxisOS](https://github.com/maxiguillermo1/MaxisOS).

### 3d. Run the installer

```bash
cd MaxisOS
bash scripts/launchme.sh
```

The script will ask short questions, for example:

- Whether the vault path is correct.
- Whether to set up **Gmail / Google Calendar** (for the **Postman** helper).

When it finishes, your vault should look roughly like this:

```
your-vault/
├── .claude/
│   ├── agents/          ← helpers for Claude Code in the terminal
│   ├── skills/          ← same helpers for Desktop / Cowork
│   └── references/      ← shared instructions
├── CLAUDE.md            ← how Claude should behave in this vault
├── .mcp.json            ← only if you enabled mail/calendar connectors
├── MaxisOS/             ← this project (use `git pull` here to update)
└── … your notes …
```

**Installer problems?** The most common issue is **Git** not installed. Install it from the link in the table above, then run Step 3 again. If you are stuck, ask someone comfortable with computers to run the two commands in **3c** and **3d** for you.

---

## Step 4: Open Claude Code **in your vault folder**

Claude Code must use your **vault** as the working folder—not the `MaxisOS` subfolder only, and not your Desktop.

**Terminal:**

```bash
cd /path/to/your-vault
claude
```

**Desktop (Cowork):** Open your **vault** folder as the project / workspace.

If Claude Code is pointed at the wrong folder, the helpers will not see your notes.

---

## Step 5: Initialize your vault

In the Claude Code chat, type exactly:

> **Initialize my vault**

The **Architect** helper starts onboarding. Typical topics:

**About you**

- What to call you  
- Preferred language  
- What you do (work, study, etc.)  
- What you want help with  

**About the vault**

- New vault vs. existing notes  
- Which helpers you want active  
- Which areas of life you want to organize  

**Connections (optional)**

- Email triage (Gmail)  
- Calendar (Google Calendar)  

When onboarding finishes, the Architect creates folders, saves your profile, and usually leaves a short welcome note.

---

## Step 6: Try it on day one

You do not need special commands. Examples:

| Say this | What usually happens |
|----------|----------------------|
| *Save this: …* | **Scribe** turns it into a note in your inbox area. |
| *Quick notes: …* (several items) | **Scribe** splits them into separate notes when that makes sense. |
| *Check my email for anything important* | **Postman** reads Gmail (if connected) and summarizes. |
| *Triage my inbox* | **Sorter** moves inbox notes into the right folders. |
| *What do I know about …?* | **Seeker** searches your vault and answers with references. |

More ideas: [Examples](examples.md).

---

## Step 7: Simple habits (optional)

| When | Say |
|------|-----|
| Morning | *What’s on my calendar today?* (if Postman is set up) |
| Any time | *Save this: …* |
| Evening | *Triage my inbox* |
| Weekly | *Weekly review* or *Run the weekly review* |

---

## Troubleshooting

### “Nothing happens” or “the helper doesn’t run”

1. Confirm Claude Code is opened with **`your-vault`** as the project folder (Step 4).  
2. Check that `.claude/agents/` exists **inside** `your-vault`.  
3. On Desktop, also check `.claude/skills/`.  
4. Rephrase your request; helpers understand normal language in many languages.

### Gmail or Calendar does not work

Postman needs the mail/calendar connectors. Run the installer again from the `MaxisOS` folder:

```bash
cd /path/to/your-vault/MaxisOS
bash scripts/launchme.sh
```

Say **yes** when asked about Gmail/Calendar, then approve access when Claude Code prompts you.

### My folders look different from the docs

The **Architect** customizes layout from your onboarding answers. That is expected.

### Update MaxisOS after `git pull`

```bash
cd /path/to/your-vault/MaxisOS
git pull
bash scripts/updateme.sh
```

This updates project files only, not your personal notes.

### A helper did something unexpected

Open an issue on the project’s GitHub and include: what you said, what happened, what you wanted.

### Change your profile later

Say: **Update my profile** and follow the Architect’s prompts.

---

## Where to go next

- **[Examples](examples.md)** — concrete “you say / what happens” scenarios  
- **[Mobile access](mobile-access.md)** — use MaxisOS from your phone (computer stays on)  
- **[Meet the helpers](agents/)** — what each role is for  
- **[Contributing](../CONTRIBUTING.md)** — improve MaxisOS  

---

*The best system is one you actually use. Start small, talk in plain language, and let the helpers handle filing when you want them to.*
