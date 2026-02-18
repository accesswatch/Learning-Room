# Merge Conflicts
## Understanding, Preventing, and Resolving Conflicts

> Merge conflicts sound intimidating but are a normal, manageable part of collaborative development. This guide explains what conflicts are, how to read conflict markers, and how to resolve them — step by step.

---

## What Is a Merge Conflict?

A merge conflict occurs when two people have both changed the **same part of the same file** in **different ways**, and Git cannot automatically decide which version is correct.

Git can merge changes automatically when they touch different parts of a file. Conflicts only happen when two changes overlap — for example:
- Person A changed line 12 to say "Submit form"
- Person B changed line 12 to say "Send message"
- Git asks: which one do you want to keep?

---

## Why Conflicts Happen

The most common causes:

| Cause | Example |
|-------|---------|
| Two people edited the same line | You both fixed the same typo differently |
| One person deleted a file but another edited it | You removed an old function; they fixed a bug in it |
| Two people restructured the same section | You reorganized a list; they added items to it |
| A long-running PR diverged from main | Your branch is weeks old and main has changed significantly |

---

## How to Prevent Conflicts (Prevention is Easier Than Resolution)

Avoiding conflicts in the first place saves time and reduces stress. Here are the most effective strategies:

### 1. **Keep your branches short-lived**

Work in small, focused chunks. A branch that lives for 3 days has far fewer conflicts than one that lives for 3 weeks.

- Target: 1-3 days from branch to merge
- If a feature takes longer, break it into smaller PRs

### 2. **Sync with main frequently**

The longer your branch diverges from main, the more likely conflicts become.

**Best practice:** Sync daily if main is active:

```bash
# From your feature branch:
git fetch origin
git merge origin/main
# Or: git rebase origin/main (if comfortable with rebasing)
```

**GitHub web method:** Use the "Update branch" button on your PR if it appears.

### 3. **Communicate with your team**

Let others know what files you're working on. Use issue comments:

> "Heads up: I'm refactoring `auth.js` in my PR for #42. If you're touching that file, let's coordinate."

Prevents two people from heavily editing the same file simultaneously.

### 4. **Avoid mass reformatting**

Running a formatter on an entire file creates conflicts with anyone else editing that file. If you must:

- Do it in a **separate PR** before functional changes
- Announce it to the team
- Merge it quickly so everyone can sync

### 5. **Pull before you push**

Always fetch and merge (or pull) before pushing your changes:

```bash
git pull origin main  # Sync your local main
git checkout your-branch
git merge main        # Merge main into your branch
git push              # Now push
```

This catches conflicts locally where they're easier to resolve.

### 6. **Work on separate files when possible**

If multiple people are working simultaneously, divide tasks by files or modules rather than everyone touching the same code.

### 7. **Keep PRs small**

A 50-file PR will almost certainly conflict with something. A 5-file PR merges quickly and cleanly.

The most effective contributors make many small PRs rather than one giant one.

### 8. **Use Draft PRs for early visibility**

Open your PR as a draft while still working. Others can see what you're changing and avoid overlapping work. Convert to "Ready for review" when done.

---

## Advanced Prevention: Understanding Fast-Forward Merges

When your branch is perfectly up to date with main and adds new commits on top, GitHub can do a "fast-forward" merge — main simply moves forward to your latest commit. No merge commit needed. No possibility of conflicts.

**How to achieve this:** Rebase your branch on main right before merging:

```bash
git checkout your-branch
git fetch origin
git rebase origin/main
git push --force-with-lease  # See warning below about force pushing
```

**Warning:** Force pushing rewrites history. Only do this on branches you alone control (not shared branches). Never force push to `main`.

For more on force pushing and rebasing, see the [Glossary](appendix-a-glossary.md#force-push).

---

## When Conflicts Are Actually Good

Conflicts indicate that multiple people are actively improving the project. In a healthy, collaborative environment, occasional conflicts are normal and manageable.

If you never have conflicts, it might mean:
- You're the only contributor (less review, less learning)
- PRs are moving too slowly (stagnation)
- People are avoiding working on important files (technical debt)

**The goal isn't zero conflicts.** The goal is catching them early, resolving them cleanly, and learning patterns that reduce future conflicts.

---

## Spotting a Conflict on GitHub

When a PR has a merge conflict, you will see this message on the Conversation tab, near the merge section:

> "This branch has conflicts that must be resolved"

You will also see a "Resolve conflicts" button. If you cannot see it (it may require write access), contact the PR author.

**Screen reader navigation to find this message:**
```
Step 1: Press D to reach the bottom of the Conversation tab
Step 2: Navigate down with H or ↓ past the comment threads
Step 3: Find the heading or region containing "This branch has conflicts"
Step 4: B to find the "Resolve conflicts" button → Enter
```

---

## Conflict Markers — What They Mean

When conflict markers appear in a file, your editor is showing you both versions of the conflicted content so you can choose. The format is always:

```
<<<<<<< HEAD
The content that is on YOUR current branch
=======
The content coming from the OTHER branch (or main)
>>>>>>> branch-name-or-commit-hash
```

**Breakdown:**
- `<<<<<<< HEAD` — the start of YOUR version (HEAD = "the branch you are currently on")
- `=======` — the dividing line between the two versions
- `>>>>>>> branch-name` — the end of the INCOMING version (from the branch being merged in)

### Example in a real file

**Original file (before conflict):**
```html
<button>Submit</button>
```

**After two conflicting changes:**
```
<<<<<<< HEAD
<button aria-label="Submit form">Submit</button>
=======
<button type="submit">Send message</button>
>>>>>>> feature/form-improvements
```

**Resolution options:**
1. Keep your version: `<button aria-label="Submit form">Submit</button>`
2. Keep their version: `<button type="submit">Send message</button>`
3. Keep both changes: `<button type="submit" aria-label="Submit form">Submit</button>` ← often the right answer

---

## Resolving Conflicts on GitHub (Web Editor)

GitHub has a built-in conflict editor that you can use without any local tools.

### Step-by-step: GitHub Conflict Editor

```
Step 1: Navigate to your PR Conversation tab
Step 2: Find the merge conflict section (navigate down with ↓ or H)
Step 3: Find the "Resolve conflicts" button (B → Enter)  
  → GitHub opens the conflict editor — a full-page text editor

Step 4: The editor shows the file(s) with conflicts
  → Navigate between conflicted files using the file list on the left
  → NVDA+F7 (or VO+U) to find the file navigation panel

Step 5: Switch to Focus Mode (NVDA+Space) to enter the text editor

Step 6: Read the conflict markers:
  → Navigate line by line with ↓
  → Find "<<<<<<< HEAD" — this marks the start
  → The dividing line is "======="
  → ">>>>>>> branch-name" marks the end

Step 7: Edit the file to your desired result:
  → Delete the conflict markers (the <<<, ===, >>> lines)
  → Keep only the lines you want in the final version
  → Do not leave any conflict markers in the file

Step 8: After editing all conflicts in this file:
  → Tab to "Mark as resolved" button → Enter

Step 9: Repeat for all conflicted files

Step 10: Tab to "Commit merge" button → Enter
  → GitHub creates a merge commit and the PR can proceed
```

### What it looks like in the editor

When the conflict editor opens, your screen reader will announce a text editor. In Focus Mode, navigate with arrow keys. The content reads:

```
<  <  <  <  <  <  <  H  E  A  D
<button aria-label="Submit form">Submit</button>
=  =  =  =  =  =  =
<button type="submit">Send message</button>
>  >  >  >  >  >  >  f  e  a  t  u  r  e  /  f  o  r  m - i  m  p  r  o  v  e  m  e  n  t  s
```

*(Note: screen readers may spell out the `<` and `>` characters letter by letter — this is normal)*

---

## Resolving Conflicts in VS Code (Day 2)

VS Code has excellent merge conflict tooling with full screen reader support. This is covered in depth in [Git & Source Control in VS Code](12-git-source-control.md), but here is an overview:

### VS Code shows conflicts as:

```
<<<<<<< HEAD (Current Change)
Your version
||||||| original                   ← (3-way merge, if enabled)
Original version before both edits
=======
Incoming version
>>>>>>> branch-name (Incoming Change)
```

### VS Code merge conflict actions

When your cursor is on a conflict region, VS Code shows **CodeLens action links** above the conflict:
- "Accept Current Change" — keeps HEAD version
- "Accept Incoming Change" — keeps the branch version
- "Accept Both Changes" — keeps both (stacked)
- "Compare Changes" — shows a side-by-side diff

**Screen reader navigation in VS Code:**
```
Step 1: Open the conflicted file
Step 2: ↓ Arrow to navigate to a conflict marker (<<<<<)
Step 3: The CodeLens links appear above — press Tab to reach them
Step 4: Press Enter on your chosen action
Step 5: Save the file (Ctrl+S)
Step 6: Stage the resolved file: Ctrl+Shift+G → find the file → Stage changes
Step 7: Commit the merge
```

**GitHub Copilot can help:** With the cursor in a conflict region, open Copilot Chat (`Ctrl+Alt+I`) and type: "Resolve this merge conflict — keep meaningful changes from both sides." Copilot will suggest a resolution that you can review and accept.

---

## When You Feel Stuck

### Ask for help — it's normal

If you are unsure which version to keep:
1. Leave a comment on the PR: "I have a merge conflict in `filename.js` and I'm not sure which version to keep — could someone help me understand the intent of these two changes?"
2. Tag the PR author or a maintainer with `@username`

### Abandon and start fresh (nuclear option)

If a conflict is severe (the branch diverged a lot from main):
1. Close the PR without merging
2. Start a new branch from the latest `main`
3. Apply only your intended changes to the new branch
4. Open a new PR

This is legitimate — not a failure.

---

## Reading a Conflict Message from Git (Command Line Reference)

If you work locally, `git merge` or `git pull` will say:

```
CONFLICT (content): Merge conflict in src/index.html
Automatic merge failed; fix conflicts and then commit the result.
```

And `git status` will show:

```
both modified: src/index.html
```

These are normal outputs. The conflict markers are inserted into the file by Git — open the file and follow the steps above.

---

## Summary Checklist

```
Before you start:
  □ My PR is small and focused (fewer conflicts = easier life)
  □ I checked that others aren't editing the same files

When you see a conflict:
  □ Don't panic — conflicts are normal
  □ Read both versions (between <<< and ===, and between === and >>>)
  □ Decide: keep one, keep both, or combine intelligently
  □ Remove ALL three conflict marker lines (<<<, ===, >>>)
  □ Verify the final file makes sense
  □ Mark as resolved → Commit merge

After resolving:
  □ Re-check that the PR description and issue link are still accurate
  □ Comment on the PR: "Resolved merge conflict — kept both the aria-label and type attribute"
  □ Request re-review if reviewers already approved before the conflict was introduced
```

---

> ### 🔥 Day 2 Amplifier — Copilot Chat & Conflict Prevention
>
> **Resolve at least one conflict completely by hand before using any AI assistance.** You must be able to read `<<<<<<<`, `=======`, and `>>>>>>>` markers and understand what each version represents. An AI-suggested resolution you cannot independently verify is a liability — you are accepting a change you do not understand into a codebase other people depend on.
>
> Once you have mastered manual conflict resolution:
> - **In VS Code** — Copilot Chat (`Ctrl+Shift+I`) can explain a conflict in plain language — *"Person A renamed the button to 'Submit Form'; Person B renamed it to 'Send Message'. Which intent should take priority?"* — but you decide what survives
> - **In your repo** — Agent Forge's `@pr-review` can identify high-risk overlapping changes before a conflict occurs, flagging when two contributors are editing the same file area and giving you time to coordinate before it escalates
> - **In the cloud** — GitHub Agentic Workflows can detect stale PRs diverging from `main` and automatically notify contributors with a suggested rebase checklist — preventing the conflict before it is ever introduced
>
> *Understanding conflict markers is not a stepping stone to letting AI handle conflicts. It is the skill that tells you when AI got it wrong.*

---

*Next: [Culture and Etiquette](07-culture-etiquette.md)*
*Back: [Working with Pull Requests](05-working-with-pull-requests.md)*
*Related: [Git & Source Control in VS Code](12-git-source-control.md)*
