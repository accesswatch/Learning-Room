# Working with Pull Requests
## Creating, Reviewing, and Merging Pull Requests with a Screen Reader

> Pull requests are where your work becomes a contribution. This guide takes you through the full pull request workflow — from opening one to participating in review — using only your keyboard and screen reader.

---

## What Is a Pull Request?

A pull request (PR) is a proposal to merge changes from one branch into another. When you have:
- Edited a file directly on GitHub (web editor)
- Made changes in your fork
- Made changes on a feature branch

...you open a PR to request that those changes be merged into the target branch (usually `main`).

A PR shows:
- **What** changed — a diff of every file
- **Why** it changed — your PR description
- **Conversation** — comments, reviews, and discussion
- **Status** — automated checks (CI/CD) and review status

---

## Navigating to Pull Requests

### From a repository:
1. `D` → "Repository navigation" landmark
2. `K` to navigate tabs → "Pull requests, [N] open"
3. `Enter` to open

### From a PR notification:
If you received a notification about a PR, follow the notification link directly to the PR page.

---

## The Pull Request List Page

The PR list works identically to the Issues list:
- `3` to navigate PR titles (they are h3 headings)
- `I` to navigate list items
- `F` to reach the search/filter field
- Filters work the same as Issues: `is:open`, `author:@me`, `review-requested:@me`, etc.

---

## Anatomy of a Pull Request Page

A PR page has three main tabs:

```
[PR title — h1]
[State badge: Open / Merged / Closed / Draft]
[Author, base ← compare, timestamp]

[ Conversation ] [ Commits ] [ Files changed ]
                                ↑ tab bar landmark

─── Conversation Tab ────────────────────────────────────────
[PR description — authored by opener]
[Status checks summary]
[Activity / review thread]
  [Review comment — h3]
  [Line comments — nested]
[Merge controls (for maintainers)]
[Comment box]

─── Commits Tab ─────────────────────────────────────────────
[List of commits, grouped by date — h3 for dates]
[Each commit as a list item with SHA, message, author]

─── Files Changed Tab ────────────────────────────────────────
[File filter search]
[File tree (left panel)]
[Diff for each file — each file is a heading]
[Line-level comment threads within diffs]
```

---

## Navigating the PR Tab Bar

The Conversation, Commits, and Files changed tabs are in a "Pull request navigation tabs" landmark.

```
Step 1: Press D → navigate to "Pull request navigation tabs"
Step 2: Press ← or → arrow keys to move between tab options
Step 3: Press Enter to activate a tab
```

**VoiceOver:**
1. `VO+U` → Landmarks → "Pull request navigation tabs"
2. `VO+Right` to move between tabs
3. `VO+Space` to activate

Each tab link reads with its name and the count: "Files changed, 3 files changed."

---

## Reading the Conversation Tab

### PR Description

1. `2` → navigate to "Description" h2 heading
2. `↓` to read the description
3. Markdown renders as semantic HTML — headings, lists, code blocks are fully accessible

### Status Checks Section

Below the description, the status checks summary shows whether automated tests passed. Look for:
- "All checks have passed" / "Some checks failed" / "Checks pending"
- A "Show all checks" button or link

```
Step 1: H or 2 to find the "Checks" or "Status checks" heading
Step 2: K to navigate links for individual check names
Step 3: Enter on a check to see details
```

See [GitHub Actions & Workflows](appendix-g-github-actions-workflows.md) for full guidance on reading status checks.

### Review Comments

Each review comment thread is an h3. Navigate with `3`:
- Hear the reviewer's username, timestamp, and their review verdict ("approved" or "requested changes")
- Then the body of their review comment
- Then any replies to that comment

To reply to a review comment:
```
Step 1: Navigate to the comment (3)
Step 2: Tab to "Reply…" link/button
Step 3: The reply text area appears — Focus Mode → type your reply
Step 4: Ctrl+Enter to submit
```

---

## Reading the Commits Tab

```
Step 1: Navigate to Commits tab (D → PR tabs → Enter)
Step 2: 3 to navigate date group headings ("Commits on April 20")
Step 3: I to navigate individual commits within a date group
Step 4: Each commit: SHA link, message, author, [Verified] badge if signed
Step 5: Enter on a commit to open its diff
```

---

## Reading the Files Changed Tab

This is the core of a code review. You will read diffs — the before/after state of every file that changed.

> **Note:** This guide uses GitHub's improved Files Changed experience (default as of January 2026), which includes proper screen reader landmarks and enhanced keyboard navigation.

### File Tree (left panel)

The file tree lists every changed file. Use it to jump directly to a specific file's diff.

```
Step 1: D → navigate to "File tree" region
Step 2: ↑/↓ to navigate the file list
Step 3: Enter to jump to that file's diff
```

### The Diff for a File

Each changed file has:
- A **file heading** (its path, e.g., "src/index.html") — navigable with `3` or `H`
- A **stats line** ("24 additions, 6 deletions")
- The **diff content** — a table where each row is one line of code

**Lines in a diff are read as:**
- `+ Added line` — line that was added
- `- Removed line` — line that was removed
- `Context line` — unchanged line shown for context

### Navigating the diff with a screen reader

**NVDA/JAWS — navigating the diff table:**
```
Step 1: T to jump to the next diff table
Step 2: Switch to Focus Mode: Insert+Space (NVDA) or Insert+Z (JAWS)
Step 3: ↓ to move through lines one by one
Step 4: Ctrl+Alt+→ to read across columns (line number | change type | content)
Step 5: The screen reader reads: "+  Add accessible name to submit button"
```

**VoiceOver — navigating the diff:**
```
Step 1: T or VO+U → Tables → select the diff table
Step 2: VO+Shift+Down to enter the table
Step 3: VO+Right/Left for columns, VO+Up/Down for rows
```

### Placing an inline comment on a diff line

1. Navigate to the specific line in the diff (using the table navigation above)
2. While focused on that line, a comment button appears — press `Enter` or `Space` to activate it
3. A comment box opens below the line
4. Focus Mode → type your comment
5. Tab to "Add single comment" button (instant comment) OR "Start a review" (to batch comments)

**Multi-line comment:**
1. Focus the first line you want to comment on
2. Press `Shift+↓` to extend the selection to additional lines
3. A comment button appears — activate it
4. The comment applies to the full range of selected lines

### Viewing comments within the diff

Inline comments appear as expandable threads within the diff table. Navigate to them with `3` (they are h3 headings). Each thread shows the comment, any replies, and a "Reply" button.

---

## Opening a Pull Request

### From the web editor workflow (editing a file on GitHub)

1. You edited a file → GitHub showed a "Propose changes" form
2. You named your branch and activated "Propose changes"
3. GitHub redirected you to the "Open a pull request" page

### From a fork or feature branch

1. Navigate to the repository
2. A "Compare & pull request" banner may appear (if you recently pushed) — activate it
3. OR: Navigate to Pull Requests tab → "New pull request"
4. Choose your base branch (what to merge into) and compare branch (your changes)

### Filling out the PR form

**Title field:**
```
Step 1: F to navigate to the title field
Step 2: Focus Mode → type a descriptive title
Step 3: Good: "Add keyboard navigation for carousel component"
Step 4: Bad: "Fix bugs"
```

**Description field:**
```
Step 1: Tab to the body text area
Step 2: Focus Mode → type using the PR template (if provided)
```

If no template, use this structure:

```markdown
## Summary

What does this PR change and why?

## Changes

- Added `aria-label` to the search button
- Fixed keyboard trap in the modal dialog
- Replaced `<div>` with `<button>` for the dismiss control

## Related Issues

Closes #42

## Testing

- Tested with NVDA + Chrome on Windows 11
- Tested with VoiceOver + Safari on macOS Sonoma
- Keyboard-only navigation verified

## Screenshots / recordings

[Include if relevant — with descriptive alt text for any images]
```

**Setting a Draft PR:**
If your work is not finished, open as a Draft:
1. After filling in the form, find the dropdown arrow next to "Create pull request"
2. Select "Create draft pull request"
3. This signals to reviewers that it is not ready for formal review yet

### Draft Pull Requests — Full Lifecycle

A **draft pull request** is a PR explicitly marked as a work in progress. It is visible to the team, can receive comments, and runs CI — but is blocked from being merged until you mark it ready.

**When to use a draft:**
- You want to show your approach and get early feedback before finishing
- You need CI to run but don't want accidental merges
- You are working across multiple days and want your progress visible
- You want to pair with a collaborator on the work

**What a draft PR does differently:**
- The merge button is disabled — even an authorized maintainer cannot merge a draft
- The PR header shows a grey "Draft" badge instead of the green "Open" badge
- Reviewers are not auto-notified (no review requests are sent until ready)
- CI workflows still run normally

**Mark a draft ready for review:**
1. Open the PR
2. Navigate to the "Reviewers" sidebar or scroll to bottom of the Conversation tab
3. Find and activate the **"Ready for review"** button
4. The draft badge changes to "Open" and reviewers are notified

**Screen reader path:**
```
Scroll to bottom of Conversation tab
→ B to navigate buttons
→ "Ready for review" button → Enter
→ Confirmation: PR status changes to Open
```

**Convert an open PR to draft (after opening):**
1. In the right sidebar, find the "Reviewers" section
2. Look for the **"Convert to draft"** link (below the review status)
3. Confirm in the dialog — this removes merge eligibility until you mark it ready again

**Requesting reviewers:**
From the sidebar Reviewers section:
1. Navigate to "Reviewers" heading (`3` or `H`)
2. Activate the gear button
3. Type a username in the search field
4. Select from the dropdown
5. Escape to save

> **Why some reviews are requested automatically:** A file called `CODEOWNERS` in many repositories maps file paths to specific people or teams. When your PR touches a file covered by a CODEOWNERS rule, GitHub automatically adds those people as required reviewers — you'll see them appear in the Reviewers sidebar without you adding them. You cannot remove a CODEOWNERS-required reviewer. If a required reviewer hasn't responded, reach out to them directly or leave a comment on the PR.

---

## Submitting a Review

When you are asked to review a PR, you have three options:
- **Comment** — leave feedback without a verdict; does not block merging
- **Approve** — signal you are satisfied; often required before merge
- **Request changes** — indicate changes must be addressed; blocks merge until resolved

### Starting a review

On the Files Changed tab, when you add inline comments, choose "Start a review" instead of "Add single comment." This batches all your comments into one review submission.

### GitHub shortcuts for pull requests

These are the GitHub built-in shortcuts for PR pages. Enable Focus Mode first (NVDA: `NVDA+Space`, JAWS: `Insert+Z`) before using single-key shortcuts.

**On the PR list page:**

| Shortcut | Action |
|---|---|
| `G P` | Jump to the Pull Requests tab from anywhere in the repo |
| `C` | Create a new pull request |
| `Ctrl+/` (Win) or `Cmd+/` (Mac) | Focus the PR search bar |

**Shortcut note:** For `G P`, press `G`, release it, then press `P` (two sequential key presses, not simultaneous).

**On an open pull request:**

| Shortcut | Action |
|---|---|
| `?` | Show all shortcuts for this page |
| `Q` | Request a reviewer |
| `M` | Set a milestone |
| `L` | Apply a label |
| `A` | Set an assignee |
| `R` | Quote selected text in your reply |
| `Ctrl+Shift+P` | Toggle Write and Preview tabs in the comment box |
| `Ctrl+Enter` | Submit comment from inside the text area |

**On the Files Changed tab:**

| Shortcut | Action |
|---|---|
| `T` | Jump to the "Filter changed files" field |
| `C` | Open the commits dropdown to filter which commits are shown |
| `Ctrl+G` (Win) or `Cmd+G` (Mac) | Insert a code suggestion block around selected code |
| `Ctrl+Shift+Enter` (Win) or `Cmd+Shift+Enter` (Mac) | Submit a review comment |

For the full shortcut system, see [Screen Reader Cheat Sheet — GitHub Shortcuts section](appendix-b-screen-reader-cheatsheet.md#github-built-in-keyboard-shortcuts).

### Suggested Changes

A **suggested change** is a special form of inline review comment where the reviewer proposes exact replacement text. The PR author can apply the suggestion directly from GitHub — no copy-paste or separate commit needed.

**As a reviewer — inserting a suggestion:**
1. On the Files Changed tab, navigate to the line you want to propose a change for
2. Activate the **line comment button** for that line (the `+` that appears on hover, or Tab to navigate to it)
3. In the comment text area that opens, press `Ctrl+G` (Windows) or `Cmd+G` (Mac)
4. GitHub wraps a suggestion block around the current line content:
   ````
   ```suggestion
   the current line content here
   ```
   ````
5. Edit the text inside the suggestion block to show your proposed change
6. Add context above the block if helpful: "This makes the alt text more descriptive:"
7. Submit as part of your review ("Start a review" → batch with other comments)

**Screen reader note:** The suggestion block is plain Markdown text in the comment editor. Type it directly:
```
```suggestion
your proposed text here
```
```
(Three backticks, the word `suggestion`, Enter, your text, Enter, three backticks.)

**As an author — applying a suggestion:**
1. Open the PR Conversation or Files Changed tab
2. Navigate to the inline comment containing a suggestion (it shows a diff-style preview)
3. Find and activate the **"Apply suggestion"** button below the suggestion block
4. GitHub creates a commit automatically that applies the change — no file editing required
5. The conversation thread is marked as resolved

**Batching multiple suggestions into one commit:**
1. For each suggestion you want to apply, activate **"Add suggestion to batch"** instead of "Apply suggestion"
2. After selecting all suggestions, activate the **"Commit suggestions"** button that appears at the top
3. GitHub applies all batched suggestions in a single commit

**When to use suggestions vs. comments:**
- Use a suggestion when you know the exact text that would fix the issue
- Use a plain comment when the change requires judgment from the author (e.g., "this alt text isn't descriptive — can you describe what the image shows?")

1. After adding all your inline comments, navigate to the review summary button
2. On Files Changed tab: find the "Review changes" button (B to navigate buttons)
3. Press Enter to open the review dialog
4. A panel opens:
   - A summary text area for overall comments
   - Radio buttons for Comment / Approve / Request changes
5. Switch to Focus Mode → type your summary comment
6. Navigate to the radio buttons with arrow keys → select your verdict
7. Tab to "Submit review" button → Enter

---

## Understanding Merge Options (for Maintainers)

When a PR is approved and checks pass, a maintainer can merge it. The merge button section appears at the bottom of the Conversation tab.

```
Step 1: Navigate to the bottom of the Conversation tab
Step 2: Find "Merge pull request" button (or similar)
Step 3: A dropdown arrow next to the button offers strategy options:
   - Create a merge commit
   - Squash and merge
   - Rebase and merge
Step 4: Choose strategy → activate the button
Step 5: Confirm in the dialog that appears
```

**After a PR is merged:**
- The PR status badge changes to "Merged" (purple)
- The source branch can be deleted — a "Delete branch" button appears
- Any linked issues with `Closes #N` in the description are automatically closed

---

## Auto-Merge — Merging When You Can't Wait Around

**Auto-merge** lets you pre-authorize a PR to merge automatically the moment all branch protection requirements are satisfied — required reviews approved, all status checks passing, and the branch up to date.

This is especially useful when:
- You've addressed all review comments and are waiting for CI to finish
- A maintainer has approved the PR but a required check is still running
- You're in a different time zone from the reviewers

### Enabling Auto-Merge on Your PR

```
1. Open your PR → scroll to the merge box at the bottom
2. Tab to the merge button dropdown arrow (next to "Merge pull request")
3. Select "Enable auto-merge"
4. Choose your merge strategy (squash, rebase, or merge commit)
5. Confirm in the dialog — the merge box now shows "Auto-merge enabled"
```

**Screen reader path:**
```
Conversation tab → End key → merge box region
Tab → dropdown button (announced as "Select merge method" or similar)
Enter → arrow keys through options → "Enable auto-merge" → Enter
Dialog: Tab → confirm button → Enter
```

**What happens next:**
- The PR merge box changes to show "Auto-merge enabled — merge will happen automatically"
- When the last required check passes (or last required review arrives), GitHub merges the PR silently
- You receive a notification: "Your PR was automatically merged"
- If a reviewer requests changes after auto-merge is enabled, auto-merge is automatically cancelled (a new approval is required before it re-enables)

### Cancelling Auto-Merge

```
Merge box → Tab → "Disable auto-merge" button → Enter
```

> **Note:** Auto-merge is only available if the repository administrator has enabled it in Settings → General. Many open source repos have it on; some do not.

---

## Practical Scenarios

### Scenario A: "I want to review an assigned PR"

```
1. Notifications → open the PR notification
2. D → PR tabs → Files changed tab
3. T → enter the first diff table → navigate lines with arrow keys
4. For each concern: activate the line comment button → type comment → Start a review
5. D → PR tabs → Conversation → scroll to bottom
6. B → "Review changes" button → type summary → select verdict → Submit review
```

### Scenario B: "I want to respond to review feedback on my PR"

```
1. Open your PR (Notifications → PR link, or find it in PR list)
2. 3 to navigate review comments
3. For each comment: read it → Tab to "Reply" → Focus Mode → type response
4. If you made a fix in code: reference the commit in your reply
5. When all addressed: Tab to "Re-request review" button → Enter
```

### Scenario C: "My PR has a merge conflict"

```
1. You will see a "This branch has conflicts that must be resolved" message near the bottom
2. Tab to "Resolve conflicts" button → GitHub opens a web conflict editor
3. The editor shows conflict markers — see Merge Conflicts guide (06-merge-conflicts.md)
4. Edit the file to resolve → Mark as resolved → Commit merge
```

---

## Common PR Mistakes to Avoid

| Mistake | Better Approach |
|---------|----------------|
| Opening a PR without an associated issue | Link to or create an issue first; comment "I'd like to work on this" |
| A vague title like "Fix things" | Be specific: "Fix missing alt text on homepage hero image" |
| Missing the PR template sections | Fill all sections — description, testing, related issues |
| Pushing many unrelated changes in one PR | One PR per logical change (smaller PRs get faster reviews) |
| Not testing your own changes | Test before requesting review |
| Not responding to reviewer comments | Acknowledge all comments, even if you disagree |

---

> ### 🔥 Day 2 Amplifier — Agent Forge: `@pr-review`
>
> **Review at least two pull requests manually before using any agent.** A review generated by `@pr-review` is only as useful as your ability to read, edit, and challenge it. The agent writes a first draft — you supply the context, the history, and the final judgment that no diff can contain.
>
> Once you have mastered manual pull request review:
> - **In VS Code** — `@pr-review review PR #N` generates line-numbered diffs with change maps, risk assessment, before/after snapshots, CI results, and suggested inline comments — a documented starting point for your own review, not a replacement for it
> - **In your repo** — Agent Forge's review capabilities work across every repository you have access to by default; fork `agent-forge` and those capabilities travel with your project from day one
> - **In the cloud** — GitHub Agentic Workflows can auto-generate PR descriptions, verify linked issues, and post accessibility impact summaries on a `pull_request` trigger — running the moment a PR is opened, whether or not anyone is watching
>
> *The agent documents the diff. You bring the context that no diff can contain.*

---

*Next: [Merge Conflicts](06-merge-conflicts.md)*
*Back: [Working with Issues](04-working-with-issues.md)*
*Related: [Accessible Code Review](14-accessible-code-review.md) | [Screen Reader Cheat Sheet](appendix-b-screen-reader-cheatsheet.md) | [Culture & Etiquette](07-culture-etiquette.md) | [GitHub Actions](appendix-g-github-actions-workflows.md)*
