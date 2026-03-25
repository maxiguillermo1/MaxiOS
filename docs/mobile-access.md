# Use MaxisOS from your phone

Your notes stay on your computer. This guide shows how to **chat with MaxisOS from your phone** while Claude Code runs **on your Mac or PC**.

---

## How this works (simple picture)

1. **On your computer:** Claude Code is running with your Obsidian vault open (same setup as normal MaxisOS use).  
2. **On your phone:** You open a **remote session** in a browser or the Claude app.  
3. **Messages** go through Anthropic’s service to reach your computer’s session; **your vault files stay local** on the computer.

```
Phone (browser or Claude app)
        ↓ messages through Anthropic
Computer (Claude Code + your vault)
        ↓ reads and writes files
Obsidian vault on disk
```

**Important:** This is **not** a separate mobile Obsidian app. If the computer is off or asleep, the phone cannot reach your vault.

---

## What you need

| Requirement | Details |
|-------------|---------|
| **Claude Code** | Version **2.1.51 or newer** (in terminal: `claude --version`) |
| **Subscription** | Claude **Pro, Max, or Team** (not API-only keys for this flow) |
| **Computer** | Stays **on**, **unlocked or awake enough** to run Claude Code, and **online** while you use the phone |
| **Phone** | Browser or Claude mobile app (iOS / Android) |
| **MaxisOS** | Already installed in your vault and tested once from the computer ([Getting started](getting-started.md)) |

**Team / Enterprise:** An admin may need to turn on Remote Control at [claude.ai/admin-settings/claude-code](https://claude.ai/admin-settings/claude-code).

---

## One-time prep on your computer

1. Open a terminal.  
2. Go to your **vault folder** (the same folder you use for MaxisOS—not only the `MaxisOS` subfolder):

```bash
cd /path/to/your-vault
```

3. Start Claude Code:

```bash
claude
```

4. The first time, complete **login** (`/login` if asked) and **accept** the workspace trust prompt for this vault.

5. Quit when finished, or leave the session—you only need to know that login and trust already worked.

---

## Start a remote session (each time you want phone access)

### Option A — Start remote control from the terminal

1. On the computer, open Terminal.  
2. Run:

```bash
cd /path/to/your-vault
claude remote-control --name "MaxisOS vault"
```

Use any short **name** you like; it helps you spot the session in a list later.

3. Leave this terminal window **open**. You should see:

- A **link** to open on your phone, and/or  
- Instructions to press **spacebar** to show a **QR code**.

### Option B — Add remote control to a session you already have

If Claude Code is already running in that vault, type in the chat:

```
/remote-control MaxisOS vault
```

Again, you can change the name.

---

## Connect from your phone

Pick one method:

| Method | What to do |
|--------|------------|
| **QR code** | On the computer terminal, press **spacebar** until a QR code appears. Scan with the phone camera or Claude app. |
| **Link** | Copy the **session URL** from the terminal and open it in the phone browser. |
| **Session list** | On the phone, open [claude.ai/code](https://claude.ai/code), find your session (often a green indicator), and tap it. |

After you connect, type (or dictate) the **same kinds of messages** you would on the computer, for example:

- *Save this: idea for next week’s team meeting*  
- *Check my email for anything urgent*  
- *What’s on my calendar tomorrow?*  
- *What do I know about the Henderson project?*

Execution still happens **on your computer**; the phone is only the remote keyboard and screen.

---

## Tips

- **Voice input** on the phone is fine; helpers are used to informal wording.  
- **Short sessions** work well (quick capture, quick checks). Long deep work is easier at the desk.  
- **Sleep:** If the computer sleeps or drops the network for a long time, the session usually ends. Adjust **Energy / sleep** settings if you need phone access while away.  
- **Mobile data** often works; Wi‑Fi is usually smoother.

---

## Troubleshooting

### “Remote Control is not yet enabled”

- For **Team/Enterprise**, ask an admin to enable Remote Control.  
- On your computer, make sure these are **not** forced on (they can block the feature):

```bash
unset CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC
unset DISABLE_TELEMETRY
```

### Session vanishes on the phone

The computer may have slept or lost the internet. Wake it, check the terminal, and start `claude remote-control` again if needed.

### Helpers do not respond like on desktop

Confirm Claude Code on the computer was started from **`/path/to/your-vault`**, not from a random folder. MaxisOS loads from that vault’s `.claude/` folder.

### QR code will not scan

Press **spacebar** to refresh the QR display. If needed, use the **URL** from the terminal instead of the code.

---

## What this is not

- **Not** a replacement for having Obsidian on the phone—your files stay on the computer unless you sync them some other way.  
- **Not** cloud storage for the vault by itself—Remote Control only forwards chat to your local session.  
- **Not** supported through generic SSH terminal apps; use the **browser** or **Claude app** as documented by Anthropic.  
- **Not** available if the computer is **off**—there is no session to attach to.

---

## Further reading

- [Claude Code Remote Control (official docs)](https://docs.anthropic.com/en/docs/claude-code/remote-control)  
- [Getting started with MaxisOS](getting-started.md)  
- [Examples](examples.md)  
