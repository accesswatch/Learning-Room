# Navigating Repositories
## A Screen Reader Guide to GitHub Repositories

> This guide covers everything you need to explore a GitHub repository using your keyboard and screen reader. No mouse required.

---

## What Is a Repository Page?

When you navigate to a GitHub repository (e.g., `https://github.com/owner/repo-name`), you land on the **repository home page** (also called the Code tab). This page has several distinct regions:

```
┌────────────────────────────────────────────────────┐
│  Navigation bar (GitHub global nav)                │
│  avatar menu | Notifications | search               │
├────────────────────────────────────────────────────┤
│  Repository header                                  │
│  owner / repo-name  (h1)                            │
│  [Star] [Watch] [Fork] buttons                      │
├────────────────────────────────────────────────────┤
│  Repository navigation tabs (landmark)              │
│  < Code > Issues  Pull requests  Actions  etc.      │
├─────────────────────────────┬──────────────────────┤
│  File tree / code panel     │  Sidebar              │
│  Branch selector            │  About section        │
│  Files table (t:table)      │  Topics               │
│  Last commit message         │  Releases             │
├─────────────────────────────┴──────────────────────┤
│  README.md (rendered)                               │
│  (a separate landmark region)                       │
└────────────────────────────────────────────────────┘
```

---

## Landing on a Repository — What to Expect

When you first navigate to a repo URL:

1. **The page title** is announced with the format: `owner/repo-name: Short description — GitHub`
2. **First heading** (`1` key) will navigate to the repo name: "owner/repo-name"
3. **The tab bar** is a landmark labeled "Repository navigation"

### Orientation sequence (do this on every new repo)

```
Step 1: Press 1 — hear the repo name
Step 2: Press D — navigate through landmarks to learn page structure
Step 3: Press NVDA+F7 (or VO+U) — scan headings to understand what's on the page
```

---

## Navigating the Repository Tabs

The five main tabs are Code, Issues, Pull Requests, Actions, and Settings (Settings only visible to maintainers).

### How to reach the tabs

**NVDA/JAWS:**
1. Press `D` to jump to the "Repository navigation" landmark
2. Press `K` or `Tab` to navigate between the tab links

**VoiceOver:**
1. `VO+U` → Landmarks rotor → navigate to "Repository navigation"
2. `VO+Right` to move through items in the landmark

### Reading the tab labels
Each tab link reads with its name and the count of items: "Issues, 14 open" or "Pull requests, 3 open." The active tab is marked with `aria-selected="true"` — your screen reader will announce it as "selected" or "current."

---

## The Files Table

The files table is the core of the Code tab — it shows every file and folder in the repo.

### Reaching the files table

Press `T` to jump to the next table on the page. The first table you will hit is usually the files table. NVDA will announce: "Table with [N] rows and 3 columns."

The three columns are:
1. **Name** — file or folder name
2. **Message** — the most recent commit message that changed this file
3. **Age** — how long ago that commit happened

### Navigating the files table

| Goal | Keys (NVDA/JAWS) | Keys (VoiceOver) |
|------|-----------------|-----------------|
| Move down one row (next file) | `Ctrl+Alt+↓` | `VO+Shift+↓` |
| Move up one row | `Ctrl+Alt+↑` | `VO+Shift+↑` |
| Move right one column | `Ctrl+Alt+→` | `VO+Shift+→` |
| Move left one column | `Ctrl+Alt+←` | `VO+Shift+←` |
| Open a file or folder | `Enter` (on the Name column) | `VO+Space` |

**Reading a row:**
Navigate to the Name column, hear the filename, then move right to read the commit message, then right again for the age. For example: "docs/ | Add accessibility guide | 3 days ago"

### Folder vs file
- Folders end with a `/` in the Name column
- When you open a folder, the page reloads showing the contents of that folder
- Press the back button or use the breadcrumb links to go back up

---

## The Branch Selector

The branch selector button sits just above the files table. It lets you switch which branch you are viewing.

### How to open the branch selector

**NVDA/JAWS:**
1. After reaching the repository navigation landmark, press `B` to navigate to buttons
2. The branch button reads: "[branch-name] branch" (e.g., "main branch")
3. Press `Enter` to open the dropdown

**VoiceOver:**
1. `Tab` to the branch button (it will be labeled with the current branch name)
2. `VO+Space` to open

### Inside the branch dropdown

```
Step 1: The dropdown panel opens — it is a live region
Step 2: A search field appears — you can type to filter branches
Step 3: Press ↓ to navigate the list of branches
Step 4: Press Enter to switch to the selected branch
Step 5: Press Escape to close without switching
```

**VoiceOver:** After activating the button, `VO+Down` to interact with the dropdown → `VO+Right` to navigate items.

---

## Viewing a Single File

When you open a file from the files table, the page shows the rendered content (for Markdown files) or the raw code (for code files).

### File page landmarks

```
D → "Repository navigation" — repo tab bar
D → "Repository header" — file breadcrumb path
D → "Main" — the file content area
D → "Repository files navigation" — contains: Raw, Blame, History buttons
```

### Reading a Markdown file (like README.md)

The README renders with full heading structure. Use:
- `H` — navigate headings within the README
- `T` — find any tables
- `L` — find lists
- `K` — navigate links

### Reading a code file

Code files render as a table where each row is one line of code. Content is read line by line.

| Goal | Keys |
|------|------|
| Read the file content | `↓` to read line by line |
| Jump to a specific line | Open Raw view (`R` button), then use browser `Ctrl+F` |
| View in Focus Mode | `NVDA+Space`, then `↓` arrows through lines |

### The file action buttons

Above the file content, there are buttons:
- **Raw** — view the file as plain text in a new page
- **Blame** — see which commit changed each line (see below)
- **History** — see the full commit history for this file
- **Edit (pencil)** — edit the file directly on GitHub (if you have write access or it's your fork)

**How to reach these buttons:**
Press `B` from within the file area, OR use `D` to navigate to the "Repository files navigation" landmark.

---

## The Blame View

Blame shows you who changed each line of a file, in what commit, and when. It is useful for tracing why a particular change was made.

### Navigating Blame

1. From a file page, activate the "Blame" button
2. The page reloads in Blame view
3. The content is a table: **left column** = commit info (who, when, message), **right column** = the line of code

```
T — jump to the blame table
Ctrl+Alt+→ — move from commit info column to code column
Ctrl+Alt+↓ — move to the next line
K — navigate the commit links (opens that commit's detail page)
```

---

## Commit History

Two ways to view history:
- **Repo-level history:** On the Code tab, find the "commits" link near the top (it shows a number like "1,234 commits"). Press `K` and navigate links to find it.
- **File-level history:** From any file page, activate the "History" button.

### Reading the Commits List Page

```
H or 3 — navigate by date headings (commits are grouped by date)
I — navigate individual commit list items
K — navigate commit links (SHA hashes, short descriptions)
Enter — open a commit to see its diff
```

### Reading a Commit Page

A commit page shows:
- The commit message (heading)
- Author and date
- Parent commit link
- A diff for every file changed

```
1 — go to commit message heading
H or 3 — navigate file headings in the diff
T — navigate to the stats table (files changed, lines added/deleted)
+ — skip table navigation and read file diffs by line
```

---

## Searching for a File

The "Go to file" shortcut is extremely useful when you know what you are looking for.

### How to use Go to File

1. Make sure you are on the Code tab of a repository
   - If hovercards are off, no navigation penalty — just navigate normally
2. Find the search box: press `F` or `E` to jump to the next edit field — look for one labeled "Go to file" or "Filter files by name"
3. Type the filename or partial path
4. Results appear as a dropdown — use `↓` to navigate, `Enter` to open

**GitHub keyboard shortcut:** `T` — opens the Go to File dialog.

**Screen reader conflict warning:** `T` normally means "next table" in NVDA/JAWS Browse Mode. GitHub's `T` shortcut conflicts with this. To use GitHub's `T` shortcut:
- **Option 1:** Switch to Focus Mode first (`Insert+Space` for NVDA, `Insert+Z` for JAWS)
- **Option 2:** Use `F` key to find the "Go to file" or "Find file" edit field instead
- **Recommended:** Option 2 is more reliable and doesn't require mode switching.

---

## GitHub Shortcuts for Repository Navigation — Spotlight

These are the GitHub built-in shortcuts you will use most on repository pages. They work by sending keystrokes directly to GitHub's JavaScript, so **enable Focus Mode first** (NVDA: `NVDA+Space`, JAWS: `Insert+Z`).

| Shortcut | What it does | When you need it |
|---|---|---|
| `?` | Show all shortcuts for this page | Any time — get the full context-specific list |
| `G C` | Jump to the Code tab | You're on Issues or PRs and want the file tree |
| `G I` | Jump to the Issues tab | You're browsing code and spot a bug to report |
| `G P` | Jump to the Pull Requests tab | You want to review open PRs |
| `G A` | Jump to Actions / workflow runs | You want to check CI status |
| `G G` | Jump to Discussions | You want to participate in project conversations |
| `G W` | Jump to Wiki | You want to view the repository wiki |

**How to use:** Press `G`, release it, then press the second letter. For example: press `G`, release, press `C` (not `G+C` together).
| `.` or `>` | Open repository in github.dev (VS Code in browser) | You want to edit a file or read code with VS Code shortcuts |
| `W` | Switch branch or tag | You want to browse a different branch of the code |
| `Y` | Expand URL to permanent canonical link | You want a link that always points to this exact commit |

**Press `?` now** on any GitHub repository page to see the live shortcut list for that specific context.

> **Screen reader tip — reading the shortcut dialog:** When the `?` dialog opens it is a modal overlay. Press `NVDA+Space` (NVDA) or ensure JAWS Virtual Cursor is active to browse the dialog content with `H` for headings and `↓` to read each shortcut. The dialog is **context-aware** — the shortcuts listed change based on the page you are on. Press `Escape` to close.

For the full shortcut system including issues, PRs, comments, and notifications, see [Screen Reader Cheat Sheet — GitHub Shortcuts section](appendix-b-screen-reader-cheatsheet.md#github-built-in-keyboard-shortcuts).

The sidebar (on desktop-width windows) contains:
- **About** — the repo description and topics
- **Releases** — recent published releases
- **Packages** — Docker/npm packages attached to the repo
- **Contributors** — the top contributors
- **Languages** — the percentage breakdown of programming languages

### Navigating the sidebar

The sidebar content is inside the "Main" landmark, after the files table and README. After the README, press `H` or `2` to reach "About" and the sidebar section headings.

**VoiceOver:** Navigate past the README section with `VO+Right` — the sidebar elements follow sequentially in the reading order.

---

## The Repository About Section

Quick way to check the project description, website link, and topics:

1. Press `D` to walk through landmarks
2. Look for a heading "About" in the sidebar
3. `2` or `H` to jump to that "About" heading
4. Then `↓` to read the description, URL, and topics

---

## Practical Scenarios

### Scenario A: "I want to find out what this project does"
1. Navigate to the repo URL
2. Press `1` — hear the repo name
3. `↓` — read the description (announced as a paragraph after the heading)
4. Navigate to README: `D` → "Repository files navigation" → `H` within the README

### Scenario B: "I want to find a good file to edit"
1. Open the files table with `T`
2. Navigate rows with `Ctrl+Alt+↓`
3. Move right with `Ctrl+Alt+→` to read the commit message (what's been changing recently)
4. When found, press `Enter` on the Name column to open the file

### Scenario C: "I want to know who has been working on this file recently"
1. Open the file
2. Activate the "Blame" button (`B` from the Repository files navigation landmark)
3. Navigate the blame table to see authors

### Scenario D: "I want to understand what changed in the last release"
1. Navigate to the sidebar "Releases" section (`H` or `2`)
2. Activate the latest release link
3. Read the release notes (rendered Markdown with headings and lists)

### Scenario E: "I want to contribute — where do I start?"
1. Navigate to the Code tab
2. Look for `CONTRIBUTING.md` in the files table
3. Open it and read the contributing guidelines
4. Then go to Issues tab and filter by `good first issue`

---

> ### 🔥 Day 2 Amplifier — Agent Forge: `@daily-briefing`
>
> **Navigate every folder of `agent-forge` manually today before using any agent.** Find `.github/agents/`, open a `.agent.md` file, and read it — that file is how an agent knows what to do. You must understand the structure before you can evaluate whether an agent understood it correctly.
>
> Once you have mastered manual repository navigation:
> - **In VS Code** — `@daily-briefing morning briefing` sweeps every repository you have access to and delivers one prioritized document: open issues, PR status, CI results, security alerts, community reactions — all without opening a browser tab
> - **In your repo** — Fork [agent-forge](https://github.com/accesswatch/agent-forge) and the `.github/agents/` folder travels with every clone; every collaborator on your fork has access to the same agents you do
> - **In the cloud** — GitHub Agentic Workflows can generate daily status reports on a schedule, running inside GitHub Actions and posting digests to a designated issue thread — no VS Code, no local setup required
>
> *An agent's output only makes sense when you already know what it is describing. You are building that knowledge right now.*

---

*Next: [Working with Issues](04-working-with-issues.md)*
*Back: [Day 1 Agenda](../DAY1_AGENDA.md)*
*Reference: [Screen Reader Cheat Sheet](appendix-b-screen-reader-cheatsheet.md)*
