---
marp: true
title: "Preliminaries — Before You Start"
description: "The accounts, tools, and concepts you need in place before Module 0 of the agentic coding workshop."
theme: gaia
class: lead
paginate: true
backgroundColor: "#fbfbfd"
color: "#1d1d1f"
style: |
  section {
    font-size: 26px;
    line-height: 1.45;
  }
  h1 { color: #0b5cad; }
  h2 { color: #0b5cad; }
  a  { color: #0b5cad; }
  /* Gaia colors bold text yellow by default — override to a dark, high-contrast
     tone so the bold weight itself carries the emphasis and stays readable. */
  strong, b { color: #0b3d6b; }
  code { background: #eef2f7; padding: 0 .3em; border-radius: 4px; color: #1d1d1f; }
  table { font-size: 22px; }
  pre { font-size: 20px; }
  .small { font-size: 20px; color: #555; }
  .ok { color: #1a7f37; font-weight: 700; }
---

<!--
Speaker notes live in HTML comments and don't render on the slide.
Render this deck with:  marp docs/slides/preliminaries.md
or open it in VS Code with the "Marp for VS Code" extension.

Audience: Bioinformatics MS students. Assume they know biology/genomics and
maybe some Python, but NOT necessarily git, GitHub, forks, or the terminal.
Pace this to the least-experienced person in the room — nobody should reach
Module 0 stuck on setup.
-->

# Preliminaries

## Before You Start

<span class="small">The accounts, tools, and ideas to have in place before Module 0 · BU Bioinformatics MS</span>

<!--
Reassure: none of this is hard, and none of it is the actual workshop. It's the
"get everyone to the same starting line" slide set. If you already have all of
it, skim and move on.
-->

---

## What you'll need — the checklist

By the end of this deck you should have:

- ✅ A **GitHub account**
- ✅ **Git** installed and working in a terminal
- ✅ **Python 3** installed (to run the example project)
- ✅ **Claude Code** installed and signed in
- ✅ A **text editor** (VS Code recommended, optional)

<span class="small">And you'll understand five ideas: the terminal, version control, GitHub, forking, and cloning.</span>

<!--
Put this checklist somewhere visible. Circle back to it at the end so people can
self-verify before Module 0.
-->

---

## Idea 1 — The terminal (command line)

A **terminal** is a text window where you type commands instead of clicking.

- macOS: **Terminal** app · Windows: **PowerShell** or **Git Bash** · Linux: your shell.
- You type a command, press Enter, read the output. That's the whole rhythm.

```
python --version        # ask python to report its version
```

<span class="small">You don't need to be a shell wizard — the workshop's guide runs most commands for you. You just need to be able to open one and read what comes back.</span>

<!--
Demystify it. Most of their agentic work will be delegated, but they must be
comfortable opening a terminal and recognizing success vs. error output.
-->

---

## Idea 2 — Version control & Git

**Version control** tracks the history of your files: every saved change, who
made it, and why. **Git** is the tool that does this.

Three words you'll hear constantly:

- **commit** — a saved snapshot of your work, with a message describing it.
- **push** — send your commits to a server (GitHub) so they're safe & shareable.
- **clone** — copy a repository from GitHub down to your computer.

<span class="small">Mental model: your files → <b>commit</b> (snapshot) → <b>push</b> (upload). The workshop turns this into muscle memory.</span>

<!--
Don't overload them with branches/merge here — just commit/push/clone. The loop
in Module 1 will reinforce commit → push. Version history = a lab notebook for
code.
-->

---

## Idea 3 — GitHub

**GitHub** is a website that hosts git repositories in the cloud.

- It's where projects live, get shared, and get collaborated on.
- You'll need a **free account**: [github.com/signup](https://github.com/signup).
- Your username is your identity for all your work in this workshop.

<span class="small">Git is the tool on your computer; GitHub is the website your work is pushed to. Related, not the same thing.</span>

<!--
Make sure everyone has an account BEFORE the live session if possible. Account
creation + email verification can eat time. This is the most common blocker.
-->

---

## Idea 4 — Forking 🍴

A **fork** is *your own personal copy* of someone else's repository on GitHub.

- The workshop repo belongs to the instructors (the **upstream** repo).
- You **fork** it → you get an identical copy under **your** account that you
  fully control.
- All your work — progress, commits, PRs — happens in **your fork**, not the
  original. That's why you have permission to push to it.

<span class="small">Think: photocopying a workbook so you can write in your own copy without touching the master.</span>

<!--
This is the concept the user flagged that students often don't know. Spend real
time here. Draw it: upstream repo → (Fork button) → your-username/repo.
Emphasize: you push to YOUR fork; you never need write access to upstream.
-->

---

## Idea 5 — Cloning ⬇️

**Cloning** downloads a repository from GitHub to your computer so you can work
on it locally.

```
git clone https://github.com/<your-username>/bioinfo-ms-claude-workshop.git
```

- Fork first (on GitHub) → **then clone your fork** (to your machine).
- The clone remembers where it came from, so `git push` sends your commits back
  up to your fork.

<span class="small">Order matters: <b>fork</b> (make your copy on GitHub) → <b>clone</b> (bring that copy local).</span>

<!--
Common mistake: cloning the upstream repo instead of their fork, then being
unable to push. Stress: clone the URL with YOUR username in it.
-->

---

## Tool 1 — Git installed

Check whether you already have it:

```
git --version
```

- <span class="ok">Prints a version</span> → you're set.
- "command not found" → install it:
  - macOS: `xcode-select --install` (or Homebrew: `brew install git`)
  - Windows: [git-scm.com/download/win](https://git-scm.com/download/win) (includes **Git Bash**)
  - Linux: `sudo apt install git` (Debian/Ubuntu) or your package manager

<span class="small">First time on a machine, set your identity: <code>git config --global user.name "..."</code> and <code>user.email "..."</code>.</span>

<!--
Have them run git --version live. The identity config matters so their commits
are attributed correctly.
-->

---

## Tool 2 — Python 3

The example project (`gc_content.py`) is Python, so you need it to *see the loop
work*.

```
python --version      # or: python3 --version
```

- Want 3.8 or newer. If missing:
  - [python.org/downloads](https://www.python.org/downloads/), or
  - conda/miniconda if that's your lab's norm.

<span class="small">No extra packages needed — the example uses only the standard library.</span>

<!--
Many bioinformatics students already have Python via conda. That's fine — just
make sure `python` or `python3` runs from their terminal.
-->

---

## Tool 3 — Claude Code

**Claude Code** is the agent you'll drive — it reads files, runs commands, edits
code, and uses git, all from your terminal.

- Install & sign-in instructions: **[claude.com/claude-code](https://claude.com/claude-code)**
- You'll need an account/subscription that includes it (check with the
  instructors about access).
- Launch it by opening a terminal **inside your cloned repo** and running its
  command — it then reads the repo (including `CLAUDE.md`) and greets you.

<span class="small">It's available in the terminal, VS Code / JetBrains, desktop, and web. The terminal in your clone is the simplest starting point.</span>

<!--
This is THE tool of the workshop. Make sure everyone can launch it and see the
greeting before Module 0. Authentication is the usual snag — sort it early.
-->

---

## Tool 4 — A text editor (recommended)

Optional, but nice for reading files and slides:

- **VS Code** ([code.visualstudio.com](https://code.visualstudio.com)) pairs
  well with Claude Code and can render these Marp decks with the **"Marp for VS
  Code"** extension.
- Any editor works. You'll mostly *read* code and markdown; the agent does most
  of the typing.

<!--
Don't let editor choice become a rabbit hole. VS Code is the safe default,
especially for the Marp preview and the Claude Code extension.
-->

---

## Putting it together

The exact sequence you'll do at the start of Module 0:

1. **Fork** the workshop repo (GitHub, in the browser).
2. **Clone** *your fork* to your computer.
3. Open a **terminal** in the clone and launch **Claude Code**.
4. It greets you and reads `PROGRESS.md` — you're in the workshop.

<span class="small">Fork → clone → launch. Three steps and you've met your guide.</span>

<!--
This slide is the bridge into Module 0. If everyone can do these four steps,
the live session runs smoothly.
-->

---

## Am I ready? ✅

Run these — if all three behave, you're ready for Module 0:

```
git --version           # prints a git version
python --version        # prints Python 3.x  (or: python3 --version)
```
- [ ] I have a **GitHub account** and know my username.
- [ ] I can **fork** and **clone** a repo (or know what those mean).
- [ ] **Claude Code** launches and signs in.

### Next up → **Module 0: Getting Started**

<!--
Do a live thumbs-up check on each box. Anyone not ready gets help now, not
mid-Module-1. Then transition straight into the Module 0 deck.
-->
