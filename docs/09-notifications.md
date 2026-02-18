# Notifications
## Managing Your GitHub Notification Inbox

> GitHub notifications are how GitHub tells you when something needs your attention. This guide teaches you to keep the inbox useful — not overwhelming — using only your keyboard and screen reader.

---

## What Generates a Notification?

GitHub sends you a notification when:

| Event | You are notified if... |
|-------|------------------------|
| Someone @mentions you | `@your-username` appears in any issue, PR, or discussion |
| A PR is assigned to you for review | You are added as a reviewer |
| An issue or PR is assigned to you | You are assigned |
| There is activity on a thread you are subscribed to | You commented, were mentioned, or chose to subscribe |
| A CI check fails on your PR | Actions sends a failure notification |
| A release is published | You are watching the repo for all activity |

---

## Notification Subscription Levels

For each repository, you choose how many notifications to receive:

| Level | What You Receive |
|-------|-----------------|
| **Participating and @mentions** | Only notifications where you participated (commented, were assigned, @mentioned). Recommended for most repos. |
| **All Activity** | Every issue opened, every comment, every PR. Only use this for your own repos or very active contribution. |
| **Ignore** | No notifications from this repo at all. |
| **Custom** | Fine-grained control: issues only, PRs only, releases, etc. |

### Changing your watch settings for a repo

From the repository page:
```
Step 1: Find the "Watch" button in the repo header
  • B to navigate buttons → find "Watch [N]" or "Unwatch" button
  • Or use D → repository header landmark
Step 2: Enter to open the dropdown
Step 3: ↑/↓ to navigate the subscription options
Step 4: Enter to select your preferred level
Step 5: The button label updates to confirm your choice
```

**Recommended setting for most repos:** "Participating and @mentions only" — you stay in the loop on what involves you without noise.

---

## The Notifications Inbox

Navigate to your inbox: `https://github.com/notifications` or press `G` then `N` (GitHub keyboard shortcut).

**Screen reader note:** The `G N` shortcut uses two sequential key presses (not simultaneous). Press `G`, release it, then press `N`. This works in Browse Mode.

### Page structure

```
[Filters sidebar on left]     ← Unread / Participating / @Mentions / Assigned / etc.
[Notification list in center] ← Each notification is a row
[Detail pane on right]        ← Preview the notification (can be disabled)
```

### Navigating the notification list

**NVDA/JAWS:**
```
Step 1: D → main content landmark
Step 2: H to navigate group headings (Today / Yesterday / This week / Older)
Step 3: Tab through individual notifications
   — each notification row announces: repo name, issue/PR title, event type, time
Step 4: Enter to open the notification (goes to the issue/PR page)
```

**VoiceOver:**
```
Step 1: VO+U → Main → navigate to notification list
Step 2: VO+Down to move through notifications
Step 3: VO+Space to open a notification
```

### What is announced per notification

> "microsoft/vscode — Add keyboard shortcut for accessible view — @username mentioned you — 2 hours ago"

Components: **repo/org** | **thread title** | **event type** | **timestamp**

---

## Inbox Actions — Keyboard Shortcuts

These shortcuts work when a notification is focused in the inbox:

| Shortcut | Action |
|----------|--------|
| `E` | Mark as done (archive from inbox) |
| `Shift+I` | Mark as read without opening |
| `Shift+U` | Mark as unread |
| `M` | Mute thread (no more notifications from this thread) |
| `S` | Save for later |
| `Enter` | Open the notification |

> **Screen reader note:** These are GitHub's own keyboard shortcuts. In Browse Mode, some of these letters are also navigation keys. To use these shortcuts reliably, make sure focus is on the notification row (tab to it) rather than in browse/reading mode.

---

## Filtering the Inbox

The left sidebar has quick filters. Use `Tab` or `K` to navigate to them:

| Filter | Shows |
|--------|-------|
| Inbox | All active notifications (default) |
| Unread | Only unread notifications |
| Saved | Notifications you saved with `S` |
| Done | Archived (marked done) notifications |
| @Mentioned | Only threads where you were directly @mentioned |
| Assigned | Issues and PRs assigned to you |
| Review requested | PRs where your review is requested |
| Participating | All threads you participated in |

### Filtering by repository or organization

At the top of the notification list there is a filter/search field:

```
Step 1: F or E to reach the filter input
Step 2: Focus Mode → type repo name or org name
Step 3: Results filter in real time
Step 4: Esc to clear the filter
```

---

## Managing Notifications at Scale

### The "mark all as done" workflow

After a busy day or coming back from time away, clear your inbox methodically:
1. Open Notifications inbox
2. Tab to "Mark all as done" button → Enter (clears everything at once)
3. Then use the "Done" filter to retrieve any you want to revisit

### Muting a noisy thread

If a thread generates too many notifications (a heated discussion, a large PR with many comments):
```
Step 1: Open the notification
Step 2: On the issue/PR page, find the "Unsubscribe" link
  • Navigate sidebar → "Notifications" section
  • Press Unsubscribe button
Step 3: Or from the inbox: focus the notification → press M
```

### Dealing with @mentions you didn't expect

If you were @mentioned in an unfamiliar thread:
1. Read the thread for context before responding
2. If it seems like a mistake, a simple "I don't think this mention was meant for me — feel free to remove it!" is enough
3. Unsubscribe after reading if you don't need to stay in the loop

---

## Notification Settings — Per Your Account

Global notification preferences are at `https://github.com/settings/notifications`.

Key settings to review:

| Setting | Recommendation |
|---------|---------------|
| **Email delivery** | Choose Participating and @mentions unless you prefer email for everything |
| **GitHub Mobile** | Enable only if you use GitHub Mobile — mobile notifications can duplicate desktop ones |
| **Watching** | "Participating and @mentions" unless you are an active maintainer |
| **Organization alerts** | Enable for orgs where you have responsibilities |

Navigate this settings page:
```
H → navigate to each settings section heading
F or E → navigate form fields within each section
Tab → move between options within a form group
```

---

## Starring vs. Watching — What Is the Difference?

New contributors often confuse these two. They appear next to each other on every repository page and do completely different things.

### Starring a Repository

| | |
|---|---|
| **What it does** | Bookmarks the repository to your Stars list at `github.com/stars` |
| **Notifications** | **None.** Starring never sends you any notifications |
| **Visibility** | Public — anyone can see what you've starred on your profile |
| **Use case** | "I want to save this for later" or "I want to show appreciation" |
| **Keyboard path** | On any repo page: `B` to navigate buttons → find "Star" button → Enter |

Starring is GitHub's equivalent of a bookmark + public endorsement. The star count on a repository is a community signal of popularity. Many maintainers watch their star count as a rough measure of interest.

### Watching a Repository

| | |
|---|---|
| **What it does** | Subscribes you to notifications from that repository |
| **Notifications** | Sends notifications based on your chosen level (see below) |
| **Visibility** | Private — other users cannot see what you're watching |
| **Use case** | "I need to stay informed about activity in this repo" |
| **Keyboard path** | `B` → find "Watch" button → Enter → ↑/↓ to pick a level → Enter |

### Common Mistake: Accidental Watching

When you comment on an issue or PR in a repository, GitHub **automatically subscribes you** to that thread — but not the whole repository. However, if you once click "Watch" on a busy repository (say, a popular open source project), you will receive a notification for every issue opened and every comment posted — potentially hundreds per day.

**How to silence a repository you accidentally over-subscribed to:**
```
Step 1: Navigate to the repository
Step 2: B → Find "Unwatch" button → Enter
Step 3: Select "Participating and @mentions"
Step 4: Enter to confirm
```

This immediately reduces notifications from that repository to only threads you personally participated in.

### Recommended Watching Strategy for This Workshop

| Repository | Recommended Watch Level |
|---|---|
| `accesswatch/agent-forge` | **Participating and @mentions** — you contribute there, you only need to hear back when someone replies to you |
| Your own fork | **All Activity** — this is your fork; know everything |
| Very busy popular repos | **Ignore** or **Participating** — do not watch for All Activity |
| Repos you're evaluating | **Star only** — save without subscribing |

---

## Screen Reader Tips for the Notification Inbox

### NVDA

- The notification list is complex — use `Tab` to navigate individual rows rather than Browse Mode arrow keys
- After marking notifications done (press `E`), the next notification automatically receives focus
- Use `NVDA+F7` → Links to get a filtered list of notification titles to scan quickly

### JAWS

- Like NVDA, use `Tab` for row navigation in the inbox
- `Insert+F6` (Headings list) to jump between date group headings (Today, This Week, etc.)
- The inbox updates in real time — JAWS will announce new notifications as they arrive

### VoiceOver

- Use `VO+U` → Landmarks → Main to reach the notification list quickly
- `VO+Space` to activate a row, `VO+Escape` to return to the list
- With Quick Nav on, `H` navigates the date group headings

---

## The GitHub Mobile App — A Reference Note

GitHub has an iOS and Android app that supports push notifications. While the app itself is not covered as a primary tool in this workshop, it is worth knowing:

- Push notifications can alert you to review requests even when you're away from your computer
- The mobile app does work with iOS VoiceOver and Android TalkBack
- For primary contribution work, the desktop browser experience remains more fully featured

---

> ### 🔥 Day 2 Amplifier — Agent Forge: `@daily-briefing`
>
> **Manage your notification inbox manually before using any agent.** The signal-versus-noise judgment you develop — what to act on, what to watch, what to mute — is the same judgment the agent applies when prioritizing its output. Without that judgment, you cannot evaluate whether the agent's prioritization is correct or whether it surfaced the things that actually matter to you.
>
> Once you have mastered manual notification management:
> - **In VS Code** — `@daily-briefing morning briefing` delivers the same information as your notification inbox, organized by priority and actionability, with the ability to reply, close, and merge from inside Copilot Chat
> - **In your repo** — Fork `agent-forge` and every collaborator on your project can run `@daily-briefing` against your shared repository; the whole team stays aligned from a single command with no inbox required
> - **In the cloud** — GitHub Agentic Workflows can run on a schedule and post a team digest to a designated issue each morning, surfacing what needs attention before anyone opens their notifications
>
> *Your notification discipline today becomes the standard the agent enforces at scale tomorrow.*

---

*Next: [Day 2 Agenda](../DAY2_AGENDA.md)*
*Back: [Labels, Milestones, and Projects](08-labels-milestones-projects.md)*
*Related: [Culture & Etiquette](07-culture-etiquette.md) | [Working with Issues](04-working-with-issues.md)*
