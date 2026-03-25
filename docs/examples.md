# MaxisOS — usage examples

This page shows **what you might say** in chat and **what usually happens** behind the scenes. Numbers and file names below are **illustrations**; your vault may look slightly different depending on how you set things up.

**You do not need to memorize phrases.** Plain language is enough; the right helper is chosen from context.

---

## Example 1: Brain dump after a meeting

**Situation:** You have several loose tasks and ideas in your head.

**You say:**

> Quick dump: Marco wants the API docs by Thursday, Lisa said the budget might be cut about 15%, I had an idea to use webhooks instead of polling for notifications, and I need to book a dentist appointment.

**What often happens:**

1. The **Scribe** helper treats this as several items.  
2. It may create separate notes such as:  
   - A task note for the API docs (deadline Thursday, link to a person note for Marco if you use those).  
   - A note about the budget comment (tags or links as appropriate).  
   - An idea note about webhooks.  
   - A personal task for the dentist.  
3. New notes usually land in **`00-Inbox/`** first, with frontmatter filled in when your setup uses it.  
4. Scribe may summarize: *“I captured four items: two tasks, one idea, one info note. Should I adjust anything?”*

---

## Example 2: Evening inbox cleanup

**Situation:** Several notes piled up in your inbox folder.

**You say:**

> Triage my inbox.

**What often happens:**

1. The **Sorter** scans notes in **`00-Inbox/`**.  
2. It reads content (and metadata if present).  
3. It moves or suggests moves, for example:  
   - Meeting-style notes → **`06-Meetings/`** (often with a date path).  
   - Project work → **`01-Projects/...`**.  
   - People-related snippets → **`05-People/`** or linked notes.  
   - Ideas → a resources or ideas area such as **`03-Resources/`**.  
4. Notes that are unclear may stay in the inbox with **questions for you**.  
5. It may update **MOC** (map of content) notes when your vault uses them.  
6. It can suggest follow-up for **Connector** (links) or other helpers.  
7. You get a **short report** of what moved and what needs a decision.

---

## Example 3: Meeting notes from a transcript

**Situation:** You have raw text from a meeting (paste or file).

**You say:**

> Transcribe this meeting. It was Q2 sprint planning with Marco, Lisa, and Ahmed, today at 10am.

Then **paste the transcript** in the same message or the next one.

**What often happens:**

1. The **Transcriber** structures the text.  
2. It may add:  
   - A short **summary**  
   - **Decisions** and **action items** (with owners/dates if visible in the text)  
   - **Topics** in order  
   - **Open questions**  
3. It links people notes when your vault uses `[[Name]]` links.  
4. It saves a file such as under **`06-Meetings/`** or **`00-Inbox/`** (depends on your rules).  
5. It may suggest a next step (for example calendar or email checks) if that fits the content.

---

## Example 4: Email check

**Situation:** You want a quick view of important mail.

**You say:**

> Check my email for anything urgent.

**Requirements:** Gmail connected through onboarding/installer (**Postman** helper).

**What often happens:**

1. **Postman** reads recent mail (scope depends on your setup).  
2. It **skips** obvious noise when it can (newsletters, promos).  
3. It **creates notes** for items that look actionable: deadlines, requests, key threads.  
4. New notes usually go to **`00-Inbox/`** for you or **Sorter** to file.  
5. You get a **summary**: what was saved, what was ignored, what needs your choice.

---

## Example 5: “What do I know about …?”

**Situation:** You need context from old notes for writing or a decision.

**You say:**

> What do I know about microservices architecture? I need to write a proposal.

**What often happens:**

1. **Seeker** searches the vault.  
2. It gathers relevant notes (meetings, projects, resources, archive).  
3. It answers in **plain language** and points to **sources** (note names or links).  
4. It may flag **gaps** (“You have little on X—consider adding research”).

---

## Example 6: Weekly review

**Situation:** You want a health pass on the vault.

**You say:**

> Run the weekly review.

(or: **Weekly review**.)

**What often happens:**

1. **Librarian** checks structure, duplicates, broken links, tags/frontmatter, MOCs, and simple stats.  
2. It may **fix** safe issues automatically and **list** items that need you.  
3. It may write a short report under something like **`Meta/health-reports/`** if your vault defines that.  
4. You get a **human-readable summary** of status and next actions.

---

## Example 7: Finding missing links

**Situation:** You want ideas for connecting notes.

**You say:**

> Analyze my vault graph and find missing connections.

(or: **Find connections for [note name]**.)

**What often happens:**

1. **Connector** scans links between notes.  
2. It reports patterns: orphans, clusters, heavily linked notes.  
3. It suggests **new links** with short **reasons** (“these two both discuss …”).  
4. You choose what to accept; nothing should silently rewrite your vault without rules you agreed to in setup.

---

## Quick reference: phrases to try

| When | Try saying | Helper |
|------|------------|--------|
| Morning | *What’s on my calendar today?* | Postman (if connected) |
| Morning | *Check my email* | Postman (if connected) |
| Any time | *Save this: …* | Scribe |
| After a meeting | *Transcribe this meeting: …* (+ paste) | Transcriber |
| Evening | *Triage my inbox* | Sorter |
| Weekly | *Weekly review* | Librarian |
| Stuck on a topic | *What do I know about …?* | Seeker |
| Organizing notes | *Find connections for …* | Connector |

---

## Remember

- **Same language you already use** is fine; helpers follow you.  
- If a result is wrong, **ask for a correction** or **narrow the request** (“only search project X”).  
- For anything critical (health, money, legal), **verify** outside the chat.

More setup detail: [Getting started](getting-started.md).
