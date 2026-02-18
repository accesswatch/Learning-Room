# Appendix L: Repository Insights
## Understanding Activity, Contributions, and Health Metrics

> GitHub's Insights tab gives you a window into a repository's activity — who's contributing, how the project is growing, what traffic it's receiving, and how healthy the codebase is. This reference covers what's available, where to find it, and how to use it both as a contributor and a maintainer.

---

## Table of Contents

1. [What Is the Insights Tab?](#1-what-is-the-insights-tab)
2. [Navigating to Insights](#2-navigating-to-insights)
3. [Pulse — Recent Activity Summary](#3-pulse--recent-activity-summary)
4. [Contributors — Who Builds the Project](#4-contributors--who-builds-the-project)
5. [Traffic — Who Visits the Repo](#5-traffic--who-visits-the-repo)
6. [Commits — Activity Over Time](#6-commits--activity-over-time)
7. [Code Frequency — Growth and Churn](#7-code-frequency--growth-and-churn)
8. [Dependency Graph](#8-dependency-graph)
9. [Network — Fork Activity](#9-network--fork-activity)
10. [Community Standards](#10-community-standards)
11. [Screen Reader Navigation](#11-screen-reader-navigation)
12. [Agent Forge: `/my-stats` and `/team-dashboard`](#12-agent-forge-my-stats-and-team-dashboard)

---

## 1. What Is the Insights Tab?

The Insights tab shows quantitative activity data for a repository. It is primarily read-only and chart-heavy — but all underlying data is also presented in tables that screen readers can navigate.

**Who can see Insights:**
- Anyone can see Insights on a public repository
- Private repository Insights require collaborator access

**What Insights does NOT show:**
- Individual user data in detail (e.g., lines per commit per person)
- Real-time data (most views update daily or weekly)
- Code quality scores

---

## 2. Navigating to Insights

From any repository:
1. Navigate to the repository's main tab bar
2. Find and select the **Insights** tab
3. The Insights sub-navigation has multiple views listed on the left (or top on smaller screens)

**Screen reader path:**
```
T → navigate the repository tab bar
→ "Insights" link → Enter
→ Left sidebar has sub-navigation: Pulse, Contributors, Traffic, Commits, etc.
→ K to navigate sidebar links → Enter to open each view
```

---

## 3. Pulse — Recent Activity Summary

**Pulse** is the Insights landing page. It summarizes activity in a chosen time period (last 24 hours, 7 days, or 30 days):

- **Open issues / Closed issues** — net change in the time period
- **Open pull requests / Merged pull requests / Closed pull requests** — with counts
- **Authors:** N contributors pushed M commits to N branches
- A list of merged PRs (each linked to the PR)
- A list of proposed PRs (open)
- A list of opened and closed issues

**What it tells you as a contributor:**
- Is this project actively maintained? (Are PRs being merged regularly?)
- Is there a backlog? (Many open issues vs. few closures)
- Is the maintainer responsive? (Time between PR open and merge)

**Screen reader navigation:**
```
2 → Section headings: "Merged pull requests", "Proposed pull requests", "Closed issues", etc.
3 → Individual PR/issue title links within each section
K → Navigate all links
```

---

## 4. Contributors — Who Builds the Project

The Contributors view shows a bar chart of commits over time, with each contributor represented by a different color. Below the chart is a sortable table.

**The table (accessible):**
- Username
- Number of commits (with a link to filtered commit history)
- Additions (lines added)
- Deletions (lines removed)
- Sorted by total commits by default

**Why this matters as a new contributor:**
- You can see how active top contributors are
- After your first merged PR, your name appears here (with your commits)
- You can link to your section (`github.com/owner/repo/graphs/contributors`) as proof of contribution

**Screen reader:**
The chart is a canvas graphic — not directly readable. The table below it is fully accessible. Navigate with `T` to reach the table, then `Tab` for sorting controls.

```
T → Contributors table
Tab → Column headers (click to sort: Commits, Additions, Deletions)
↓ → Navigate rows (each contributor is a row)
K → Links to each contributor's filtered commit list
```

---

## 5. Traffic — Who Visits the Repo

**Traffic** shows who is viewing and cloning the repository. Available only to repository owners and collaborators with push access.

**Metrics:**

| View | What It Shows |
|---|---|
| **Visitors** | Unique visitors and total page views over 14 days |
| **Git clones** | Number of times the repo was cloned (git clone, not forks) |
| **Referring sites** | Where traffic comes from (Google, Hacker News, direct, etc.) |
| **Popular content** | Which files and pages in the repo get the most views |

**Why this matters:**
- If the README is the most-viewed file, documentation improvements have high impact
- If traffic spiked when a blog post linked the repo, that's a good signal for community growth

---

## 6. Commits — Activity Over Time

A chart showing commit frequency over the past year, by week. Useful for identifying:
- Active development periods (many commits)
- Dormant periods (no commits) — a project with 6+ months of inactivity may be unmaintained
- Release sprints (burst of commits before a release tag)

**Screen reader:** The chart is visual. The underlying data is not presented in a table here. For a text-based view of commit history, use the Commits tab on the main repository page instead.

---

## 7. Code Frequency — Growth and Churn

Shows additions and deletions per week as an area chart. A healthy codebase has more additions than deletions until it matures, then stabilizes.

**Churn** (high deletions alongside high additions) can indicate:
- Heavy refactoring
- Ongoing maintenance of large files
- Active cleanup of technical debt

---

## 8. Dependency Graph

The **Dependency Graph** shows:
- What your project depends on (libraries, packages)
- What depends on your project (if others import your repo)

**Dependents** — repositories that depend on this one — is the "used by" count you see on the right sidebar of popular packages.

**Enabling/viewing:**
- Settings → Security & Analysis → Dependency graph → Enable
- Navigate to Insights → Dependency graph

**Why it matters for security:** The dependency graph feeds Dependabot. If a vulnerability is found in a library, Dependabot uses this graph to identify which repos use the affected version and opens automated PRs to update them.

---

## 9. Network — Fork Activity

The **Network** view shows a graphical branch/fork network — who has forked the repo, what branches exist, and how they diverge.

**Screen reader note:** The network graph is a canvas visualization not accessible to screen readers. The underlying fork list is accessible separately at `github.com/owner/repo/forks`.

**The forks list** (at `/forks`) is a simple table of who forked the repo — navigable with standard table navigation.

---

## 10. Community Standards

The **Community** or **Community Standards** view (found in the Insights sidebar or in the main repository homepage's "Recommended" sidebar section) shows a checklist of community health files:

| File | Purpose | Status |
|---|---|---|
| Description | One-line repo summary | ✓ or ✗ |
| README | Project overview | ✓ or ✗ |
| Code of Conduct | Community behavior standards | ✓ or ✗ |
| Contributing guide | How to contribute | ✓ or ✗ |
| License | Usage rights | ✓ or ✗ |
| Issue templates | Structured issue forms | ✓ or ✗ |
| Pull request template | PR checklist | ✓ or ✗ |
| Security policy | How to report vulnerabilities | ✓ or ✗ |

A fully green checklist signals a well-maintained project. For agent-forge contributors, **adding a missing community health file is always a welcome `good first issue` contribution.**

**Screen reader:**
```
H / 2 → "Community Standards" section heading
Tab → Each checklist item (links to add missing files)
```

---

## 11. Screen Reader Navigation

### Insights Tab Bar (sub-navigation)

```
Insights left sidebar:
K → Navigate sidebar links: Pulse, Contributors, Traffic, Commits, Code frequency, Dependency graph, Network, Forks, Community
Enter → Open that Insights view
```

### Charts and Graphs

Most Insights charts are canvas or SVG visuals. They announce as "image" or "graphic" to screen readers. **Strategy: skip the chart and use the data table or list below it**, which contains the same information in accessible form.

```
T → Jump to data tables
H → Section headings
I → List items (in Pulse views)
```

### Pulse View

```
2 → "Merged pull requests", "Opened issues", etc. sections
3 → Individual PR/issue titles
K → Links to each item
```

---

## 12. Agent Forge: `/my-stats` and `/team-dashboard`

Instead of navigating GitHub's chart-heavy Insights UI, Agent Forge provides two commands that deliver the same data in text form directly in VS Code.

### `/my-stats`

Shows your personal contribution statistics across all tracked repos:

```
/my-stats
/my-stats last 30 days
/my-stats org:accesswatch
```

Output includes:
- PRs opened and merged
- Issues filed and closed
- Reviews conducted
- Commits pushed
- Compare to previous period

### `/team-dashboard`

Shows team-wide activity across tracked repos — who contributed what, response times, review coverage:

```
/team-dashboard
/team-dashboard org:accesswatch
/team-dashboard sprint
```

Output includes:
- Per-person contribution summary
- Review coverage (how many PRs got reviews)
- Open issues by assignee
- CI health across team repos

**Use these instead of navigating the Insights UI** when you want contribution data without leaving VS Code and without dealing with canvas charts.

---

*Return to: [Resources](appendix-q-resources.md) | [Glossary](appendix-a-glossary.md)*
