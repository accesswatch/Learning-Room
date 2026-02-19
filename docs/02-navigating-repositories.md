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

The main tabs are: **Code**, **Issues**, **Pull Requests**, **Discussions**, **Actions**, **Projects**, **Wiki**, **Security**, **Insights**, and **Settings** (Settings only visible to maintainers). Not all tabs appear on every repository — Discussions, Wiki, and Projects must be enabled by the repository owner.

### How to reach the tabs

<details>
<summary>🖥️ Visual / mouse users</summary>

The tab bar is visible just below the repository name. Click the tab you want — **Code**, **Issues**, **Pull requests**, etc. The active tab is underlined. The number next to a tab (e.g., "Issues · 14") shows how many open items are in that section.

</details>

<details>
<summary>🔊 Screen reader users (NVDA / JAWS)</summary>

1. Press `D` to jump to the **"Repository navigation"** landmark
2. Press `K` or `Tab` to navigate between the tab links

</details>

<details>
<summary>🔊 Screen reader users (VoiceOver)</summary>

1. `VO+U` → Landmarks rotor → navigate to **"Repository navigation"**
2. `VO+Right` to move through items in the landmark

</details>

### Reading the tab labels
Each tab link reads with its name and the count of items: "Issues, 14 open" or "Pull requests, 3 open." The active tab is marked with `aria-selected="true"` — your screen reader will announce it as "selected" or "current."

---

## The Files Table

The files table is the core of the Code tab — it shows every file and folder in the repo.

### Reaching the files table

<details>
<summary>🖥️ Visual / mouse users</summary>

The file table is the main panel of the Code tab, showing folders and files with their most recent commit message and how long ago each was changed. It’s visible immediately below the branch selector. Click any folder name to open it, or click a file name to view the file.

</details>

<details>
<summary>🔊 Screen reader users</summary>

Press `T` to jump to the next table on the page. The first table you will hit is usually the files table. NVDA will announce: “Table with [N] rows and 3 columns.”

</details>

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

<details>
<summary>🖥️ Visual / mouse users</summary>

Mouse users see the current branch name as a button with a dropdown arrow (e.g., `main ▼`) just above the file table. Click it to open the branch list. Type to filter branches, then click a branch name to switch.

</details>

<details>
<summary>🔊 Screen reader users (NVDA / JAWS)</summary>

1. After reaching the repository navigation landmark, press `B` to navigate to buttons
2. The branch button reads: “[branch-name] branch” (e.g., “main branch”)
3. Press `Enter` to open the dropdown

</details>

<details>
<summary>🔊 Screen reader users (VoiceOver)</summary>

1. `Tab` to the branch button (it will be labeled with the current branch name)
2. `VO+Space` to open

</details>

### Inside the branch dropdown

```
Step 1: The dropdown panel opens — it is a live region
Step 2: A search field appears — you can type to filter branches
Step 3: Press Tab to move to the results list
Step 4: Press ↓/↑ or Tab/Shift+Tab to navigate the list of branches
Step 5: Press Enter to switch to the selected branch
Step 6: Press Escape to close without switching
```

To return to the search field from the list: navigate to the tabs control at the top of the dropdown ("Branches" and "Tags" tabs), then use `Shift+Tab`.

**VoiceOver:** After activating the button, `VO+Down` to interact with the dropdown → `VO+Right` to navigate items.

### Switching to a tag

Tags mark specific releases or versions. The branch dropdown also provides tag navigation:

1. Open the branch button (same steps as above)
2. Inside the dropdown, navigate to the **tabs control** at the top (reads as "Branches tab" and "Tags tab")
3. Use `←/→` to switch to the **Tags** tab
4. `Tab` to move to the tags list
5. Navigate with `↑/↓` and press `Enter` to select a tag

The repository page reloads showing the code at that tagged version.

---

## Cloning a Repository

Cloning copies the repository to your local machine so you can work with it in VS Code or the terminal.

<details>
<summary>🖥️ Visual / mouse users</summary>

1. On the repository’s main page (Code tab), find and click the green **Code** button above the file table
2. A popover opens showing **HTTPS**, **SSH**, and **GitHub CLI** tabs
3. Click the **HTTPS** tab (default) and click the **copy** icon next to the URL
4. Open your terminal, `cd` to where you want the folder, and run `git clone <pasted-URL>`
5. Alternatively, click **Download ZIP** to get a one-time archive without Git

</details>

<details>
<summary>🔊 Screen reader users</summary>

1. Press `1` or `Shift+1` to navigate to the repository h1 heading
2. Press `B` to navigate to the next button — look for the **“Code”** button
3. Press `Enter` or `Space` to open the Code flyout panel
4. The flyout has tabs: **HTTPS**, **SSH**, **GitHub CLI**
5. `Tab` to the HTTPS tab or SSH tab according to your preference
6. `Tab` to the “Copy url to clipboard” button and press `Enter`
7. The URL is now in your clipboard — paste it into VS Code or your terminal

**Alternative:** `Tab` further to find **Download ZIP** if you want a one-time copy without Git.

> **VoiceOver:** After activating the Code button, interact with the flyout panel with `VO+Shift+Down`. Use `VO+Right` to move to HTTPS/SSH tabs and `VO+Space` to select.

</details>

---

## Watching, Starring, and Forking

These three actions let you follow, bookmark, or copy a repository.

### Watching (subscribe to notifications)

<details>
<summary>🖥️ Visual / mouse users</summary>

The **Watch**, **Star**, and **Fork** buttons are at the top-right of the repository page, just below the global navigation bar. Click **Watch** to open a dropdown of subscription options: **Participating and @mentions**, **All Activity**, or **Ignore**. Select your preference and click **Apply**.

</details>

<details>
<summary>🔊 Screen reader users</summary>

1. Press `L` to navigate through list items to reach the **Main** landmark
2. Continue pressing `L` until you find the **Watch** button (reads as “Watch this repository”)
3. Press `Enter` to open the subscription submenu
4. Press `↑/↓` to browse options: Participating, All Activity, Ignore
5. Press `Enter` to confirm

</details>

### Forking (create your own copy)

<details>
<summary>🖥️ Visual / mouse users</summary>

Click the **Fork** button (top-right, next to Watch and Star). A page opens asking you to choose the owner and repository name for your fork. Fill in the details and click **Create fork**.

</details>

<details>
<summary>🔊 Screen reader users</summary>

1. Press `L` to navigate list items in the Main landmark
2. Press `I` to navigate individual list items until you find “Fork your own copy”
3. Press `Enter` to start the fork workflow
4. The fork creation page lets you choose the owner and repository name
5. Tab to “Create fork” and press `Enter`

</details>

### Starring (bookmarking)

<details>
<summary>🖥️ Visual / mouse users</summary>

Click the **Star** button (top-right). The button changes to **Starred** with a filled star icon to confirm. Click it again to unstar.

</details>

<details>
<summary>🔊 Screen reader users</summary>

1. Press `L` to navigate list items in the Main landmark
2. Press `I` to navigate individual list items until you find “Star this repository”
3. Press `Enter` or `Space` to star
4. The button text changes to “Unstar” on the next focus

> **Tip:** If the Watch/Fork/Star area is not immediately found with `L`, press `D` to navigate to the **Main** landmark first, then use `I` to browse list items within that region.

</details>

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

### Editing a file

<details>
<summary>🖥️ Visual / mouse users</summary>

1. Open the file you want to edit
2. Click the **pencil icon** (Edit file) in the top-right of the file content area
3. The file opens in a web editor — click in the content area and edit
4. When done, scroll down to “Commit changes”, type a commit message, and click the green **Commit changes** button
5. Choose “Commit directly to `main`” (or your branch) and confirm

</details>

<details>
<summary>🔊 Screen reader users</summary>

1. Open the file you want to edit
2. Press `K` to navigate links until you find the **“Edit file”** link (may be labeled with a pencil icon description)
3. Press `Enter` to activate the link — the page opens in edit mode with a code editor textarea
4. Switch to Focus Mode: press `NVDA+Space` (NVDA) or `Insert+Z` (JAWS)
5. Make your changes using standard text editing keys
6. When done, press `Escape` to exit the textarea
7. Press `Shift+Tab` to navigate backwards to the **“Commit Changes”** button
8. Press `Enter` to open the commit dialog
9. Type your commit message in the dialog, then Tab to the confirm button and press `Enter`

> **Note:** Switch back to Browse Mode after step 6 (`NVDA+Space`) to use `Shift+Tab` more reliably to reach the commit button.

</details>

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

## Try It: The Five-Tab Tour

**Time:** 3 minutes | **What you need:** Browser with screen reader, signed in to GitHub

Navigate to [github.com/accesswatch/agent-forge](https://github.com/accesswatch/agent-forge) and do this:

1. **Code tab** — Press `D` to the "Repository navigation" landmark, then `K` to find "Code". Press `Enter`. You're on the file list.
2. **Issues tab** — Press `G` then `I` (Focus Mode first: `NVDA+Space`). How many open issues are there? Press `3` to jump through issue titles.
3. **Pull Requests tab** — Press `G` then `P`. Are there any open PRs?
4. **Find a file** — Press `T` (in Focus Mode) to open the file finder. Type `README` and press `Enter`. You just navigated straight to a file without scrolling.
5. **Read the README** — Press `1` to find the page title, then `2` to scan sections.

**You're done.** You just toured a real repository using only your keyboard.

> **What success feels like:** You visited four tabs and opened a file without touching a mouse. Every repository on GitHub has this same layout — you now know how to navigate all of them.

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

*Next: [The Learning Room](03-the-learning-room.md)*
*Back: [Understanding GitHub's Web Structure](01-understanding-github-web-structure.md)*
*Reference: [Screen Reader Cheat Sheet](appendix-b-screen-reader-cheatsheet.md)*
