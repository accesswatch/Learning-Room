# Pre-Workshop Setup
## Everything You Need Before Day 1 Begins

> **Please complete this guide at least one day before the workshop.** If you run into any issues, contact the event organizers so we can help — we want Day 1 to start with everyone ready to go, not troubleshooting.

---

## Table of Contents

1. [What You Will Need](#1-what-you-will-need)
2. [Step 1 — Create Your GitHub Account](#2-step-1--create-your-github-account)
3. [Step 1.5 — Configure Git Identity (If Using Git Locally)](#3-step-15--configure-git-identity-if-using-git-locally)
4. [Step 2 — Configure GitHub Accessibility Settings](#4-step-2--configure-github-accessibility-settings)
5. [Step 3 — Configure Your Profile](#5-step-3--configure-your-profile)
6. [Step 4 — Verify Modern GitHub Interface](#6-step-4--verify-modern-github-interface)
7. [Step 5 — Test Your Screen Reader on GitHub](#7-step-5--test-your-screen-reader-on-github)
8. [Step 6 — Install Visual Studio Code (Day 2)](#8-step-6--install-visual-studio-code-day-2)
9. [Step 7 — Install GitHub Copilot in VS Code (Day 2)](#9-step-7--install-github-copilot-in-vs-code-day-2)
10. [Step 8 — Verification Checklist](#10-step-8--verification-checklist)
11. [Other GitHub Access Methods (Reference Only)](#11-other-github-access-methods-reference-only)
12. [Getting Help Before the Event](#12-getting-help-before-the-event)

---

## 1. What You Will Need

### Hardware
- A computer running Windows or macOS
- A reliable internet connection
- Headphones (recommended — screen reader audio during group sessions)

### Software — Day 1
- A modern web browser: **Chrome** or **Firefox** recommended
  - Both have strong compatibility with GitHub's interface and screen readers
  - Edge is also acceptable on Windows
  - Safari is the recommended browser on macOS with VoiceOver
- A screen reader (see options below)
- A GitHub account (free tier is fine)

### Software — Day 2 (additional)
- **Visual Studio Code** (free) — [download here](https://code.visualstudio.com/)
- **GitHub Copilot extension** for VS Code — installed from within VS Code
- A GitHub Copilot subscription or Free tier access (Copilot Free is available to all GitHub users)

### Screen Reader Options

You only need **one** of these. Use whichever you are most comfortable with.

| Screen Reader | Platform | Cost | Download |
|---------------|----------|------|----------|
| **NVDA** (NonVisual Desktop Access) | Windows | Free | [nvaccess.org](https://www.nvaccess.org/download/) |
| **JAWS** (Job Access With Speech) | Windows | Paid (trial available) | [freedomscientific.com](https://www.freedomscientific.com/products/software/jaws/) |
| **VoiceOver** | macOS / iOS | Built-in (free) | Included with macOS — press `Cmd+F5` to activate |

> **Note:** All workshop exercises are designed to work with any of these screen readers. Where specific key commands differ, we will note all three. You are not disadvantaged by using any particular screen reader.

---

## 2. Step 1 — Create Your GitHub Account

If you already have a GitHub account, skip to [Step 2](#3-step-2--configure-github-accessibility-settings).

### Create an account

1. Open your browser and navigate to **https://github.com/signup**
2. Follow the prompts — you will need:
   - A username (this is your public identity on GitHub — choose thoughtfully)
   - An email address
   - A password
3. Verify your email address — GitHub will send you a confirmation link
4. When asked about plans, choose **Free** — it includes everything we need for this workshop

### Choosing a username

Your username appears on every issue, PR, and comment you make. A few guidelines:
- Use lowercase letters, numbers, and hyphens only
- Keep it professional — it represents you in the open source community
- You can change it later, but it will break existing links to your profile

### Enable two-factor authentication (strongly recommended)

1. Navigate to [Settings → Password and authentication](https://github.com/settings/security)
2. Under "Two-factor authentication," select **Enable**
3. Follow the setup for an authenticator app or passkey
4. Save your recovery codes somewhere secure

> **Screen reader note:** The 2FA setup flow uses QR codes for authenticator apps. If your screen reader cannot read a QR code, choose the "Enter key manually" option — GitHub provides the secret as a text string you can type into your authenticator app.

---

## 3. Step 1.5 — Configure Git Identity (If Using Git Locally)

> **Important:** If you plan to use Git from VS Code or the command line (Day 2), you must configure your identity first. If you're only using the GitHub web interface, you can skip this section.

Git needs to know who you are so every commit you make is attributed to you. This affects how your name appears in project history.

### Configure in VS Code (Recommended for This Workshop)

1. Open **Visual Studio Code**
2. Open the integrated terminal:
   - Menu: **Terminal → New Terminal**
   - Keyboard: `` Ctrl+` `` (Windows) or `` Cmd+` `` (Mac)
3. Type the following commands, replacing with your information:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

**What to use:**
- **user.name:** Your real name or the name you want shown on commits (e.g., "Jane Smith")
- **user.email:** The email address associated with your GitHub account (must match exactly)

**Screen reader note:** The terminal in VS Code is accessible with all major screen readers. Press `` Ctrl+` `` to move focus to the terminal, type your commands, and press `Enter`.

### Why This Matters

Every commit you make includes:
- Your name
- Your email address  
- A timestamp
- The commit message

If Git isn't configured, it will either:
- Use a default name like "Unknown" (looks unprofessional in project history)
- Refuse to create commits with an error message

### Verify Your Configuration

Run this command to see your current settings:

```bash
git config --global --list
```

You should see:
```
user.name=Your Name
user.email=your-email@example.com
```

### Using the Correct Email

Use the same email you registered with GitHub. If you're concerned about privacy, GitHub offers a no-reply email you can use: `username@users.noreply.github.com` — find it in [Settings → Emails](https://github.com/settings/emails).

**When to configure this:** Before your first commit in VS Code. You can skip it on Day 1 if you're only working through the GitHub web interface.

---

## 4. Step 2 — Configure GitHub Accessibility Settings

These settings make GitHub significantly more usable with a screen reader. Do not skip this section.

### Navigate to Accessibility Settings

1. Sign into GitHub
2. Navigate directly to [Settings → Accessibility](https://github.com/settings/accessibility) — fastest path, works for all users
   - Keyboard menu path: press `D` to cycle page landmarks to "Navigation Menu," press `K` to reach "Settings," and press `Enter`. On the Settings page, press `D` to reach the sidebar, then `K` to find "Accessibility."

### Recommended accessibility settings

| Setting | Recommended Value | Why |
|---------|-------------------|-----|
| **Link underlines** | Enabled | Improves link visibility; also helps screen reader users distinguish links in browse mode |
| **Hovercards** | **Disabled** | Hovercards announce their keyboard shortcut (`H`) every time you pass over a link, adding significant verbosity and slowing navigation. **Turn this off.** |
| **Character key shortcuts** | Your preference | Single-key shortcuts speed up navigation but can conflict with screen reader keys — see [Screen Reader Cheat Sheet](appendix-b-screen-reader-cheatsheet.md) |
| **Tab size** | 4 (default) | Affects how code renders in the diff view |

### How to disable hovercards

1. Navigate to [Settings → Accessibility](https://github.com/settings/accessibility)
2. Find "Link previews" or "Hovercards"
3. Toggle it **off**
4. This is the single highest-impact accessibility setting for screen reader users on GitHub

### Theme settings

1. Navigate to [Settings → Appearance](https://github.com/settings/appearance)
2. GitHub offers:
   - **Light default** — standard white background
   - **Dark default** — dark background
   - **High contrast light** — maximum contrast for low vision
   - **High contrast dark** — maximum contrast on dark background
   - **Colorblind modes** — Protanopia, Deuteranopia, Tritanopia variants
3. Choose what works best for you — high contrast themes are recommended if you have any low vision characteristics

---

## 5. Step 3 — Configure Your Profile

Your GitHub profile is your public identity in the open source community. Setting it up properly helps maintainers know who you are.

### Update your profile

1. Navigate to [Settings → Public profile](https://github.com/settings/profile)
2. Fill in:
   - **Name** — your real name or display name (not the same as your username)
   - **Bio** — a short description (e.g., "Accessibility advocate and open source contributor")
   - **Location** — optional but builds trust in the community
   - **Website or social links** — optional
   - **Pronouns** — GitHub supports adding pronouns to your profile

### Add a profile picture (optional)

A profile picture humanizes your contributions. It can be a photo or any image. If you prefer not to use a photo, GitHub generates a default avatar based on your username.

### Set your notification email

1. Navigate to [Settings → Notifications](https://github.com/settings/notifications)
2. Add a **custom routing** email if you want GitHub notifications to go to a different address than your account email

---

## 6. Step 4 — GitHub Interface (No Action Needed)

**Good news:** As of January 2026, GitHub's improved Issues and Pull Request experiences are enabled by default for all users. You don't need to enable any feature previews.

You automatically get:
- **Modern Issues experience** with proper heading hierarchy and better screen reader navigation
- **Improved Files Changed experience** with enhanced keyboard navigation and screen reader landmarks

These improvements are now the standard GitHub interface. If for any reason you need to switch back to the classic experience, you can opt out in your [Feature preview settings](https://github.com/settings/feature_previews).

---

## 7. Step 5 — Set Up Your Screen Reader & Browser

### NVDA (Windows)

**Install NVDA** if you haven't already:
1. Download from [nvaccess.org/download](https://www.nvaccess.org/download/)
2. Run the installer — you can install to your computer or run portably
3. After launch, NVDA speaks "NVDA started" when running

**Configure NVDA for web browsing:**
1. Open NVDA Menu (`NVDA+N`)
2. Go to **Preferences → Settings → Browse Mode**
3. Enable "Use screen layout" — this helps with GitHub's landmark navigation
4. Under **Document Formatting**, disable announcements you find too verbose

**Recommended NVDA voice settings:**
- Rate: 60–75% (fast enough to be efficient, slow enough to be clear)
- Punctuation: "Most" (reads important symbols like `#` and `@` without reading every period)

**Your NVDA key:** By default it is `Insert`. It can also be set to `Caps Lock` in NVDA preferences if that is more comfortable.

---

### JAWS (Windows)

**If using a trial:** JAWS runs in 40-minute sessions without a license. Restart it if you need more time.

**Configure JAWS for web browsing:**
1. Open JAWS Settings Center: `Insert+F2 → Settings Center`
2. Ensure "Virtual cursor" is active for web browsing
3. In Chrome or Firefox, JAWS should automatically activate Virtual/Browse mode

**Recommended JAWS settings for GitHub:**
- Verbosity → Links: Read link text only (disable "opens in new window" if too verbose)
- Verbosity → Punctuation: "Most" for same reason as NVDA

**Your JAWS key:** `Insert` (or `Caps Lock` if using laptop layout)

---

### VoiceOver (macOS)

**Activate VoiceOver:** `Command+F5` toggles VoiceOver on and off.

**Essential VoiceOver setup for web:**
1. Open VoiceOver Utility: `VO+F8`
2. Go to **Web** category → **Web Rotor**
3. Ensure these are checked: Headings, Landmarks, Links, Buttons, Form Controls, Tables
4. **Recommended browser:** Safari (best VoiceOver integration on macOS)
5. Firefox on macOS also has good VoiceOver support

**Your VoiceOver modifier key:** `VO` = `Control+Option` by default.

**Turn on Quick Nav for fast navigation:**
- Press `Left Arrow + Right Arrow` simultaneously to toggle Quick Nav
- With Quick Nav on: `H` = next heading, `L` = next link, `B` = next button (same as NVDA/JAWS browse mode keys)

---

### Browser Recommendations Summary

| Browser | Windows | macOS | Notes |
|---------|---------|-------|-------|
| **Chrome** | ✅ Recommended | ✅ Good | Best with NVDA and JAWS |
| **Firefox** | ✅ Recommended | ✅ Good | Excellent accessibility support on all platforms |
| **Edge** | ✅ Acceptable | ✅ Acceptable | Chromium-based; works well |
| **Safari** | ❌ Not available | ✅ Recommended | Best for VoiceOver on macOS |

**Before the workshop:** Open GitHub.com in your chosen browser with your screen reader running and confirm you can navigate the page using heading keys.

---

## 8. Step 6 — Install Visual Studio Code (Day 2)

Visual Studio Code (VS Code) is the development environment we use on Day 2. It is free, open source, and has excellent built-in accessibility support.

### Download and install

1. Navigate to [code.visualstudio.com](https://code.visualstudio.com/)
2. Select the download link for your operating system
3. Run the installer with default options

### Enable Screen Reader Mode in VS Code

This is the single most important VS Code accessibility setting:

1. Open VS Code
2. Press `Shift+Alt+F1` — this toggles **Screen Reader Optimized** mode
   - VS Code will prompt you on first launch if it detects a screen reader
   - Alternatively: Open Command Palette (`Ctrl+Shift+P`), type "Toggle Screen Reader Accessibility Mode," press `Enter`
3. Confirm the status bar at the bottom shows "Screen Reader Optimized"

**What Screen Reader Mode changes:**
- Switches the editor to a text-only rendering mode that screen readers can read linearly
- Enables audio cues for inline suggestions, errors, and breakpoints
- Adjusts how diffs are presented for linear reading

### VS Code keyboard basics (we will cover these fully on Day 2)

| Action | Shortcut |
|--------|----------|
| Open Command Palette | `Ctrl+Shift+P` |
| Open file | `Ctrl+P` |
| Open terminal | `Ctrl+`` ` (backtick) |
| Focus Explorer panel | `Ctrl+Shift+E` |
| Focus editor | `Ctrl+1` |

---

## 9. Step 7 — Install GitHub Copilot in VS Code (Day 2)

### Sign in to GitHub in VS Code

1. Open VS Code
2. Open the Command Palette (`Ctrl+Shift+P`) and type "Sign in to GitHub"
3. Follow the browser authentication flow
4. Return to VS Code — you should be signed in

### Install the GitHub Copilot extension

1. Press `Ctrl+Shift+X` to open the Extensions panel
2. Type "GitHub Copilot" in the search box
3. Find **GitHub Copilot** (publisher: GitHub) and press `Enter` on **Install**
4. The **GitHub Copilot Chat** extension installs automatically alongside it

### Verify Copilot is working

1. Open any text file in VS Code
2. Start typing — Copilot will suggest completions in grey text
3. Press `Tab` to accept a suggestion, `Esc` to dismiss
4. If you see a Copilot icon in the status bar (bottom), you are connected

### Copilot Free tier

Copilot Free is available to all GitHub users at no cost. It includes:
- Limited inline code completions per month
- Limited Copilot Chat messages per month

For this workshop, Free tier is sufficient. If you want unlimited access, paid plans are available at [github.com/features/copilot#pricing](https://github.com/features/copilot#pricing).

---

## 10. Step 8 — Verification Checklist

Work through this checklist before Day 1. Check off each item:

```
Pre-Workshop Checklist

GITHUB ACCOUNT
[ ] GitHub account created and email verified
[ ] Two-factor authentication enabled
[ ] Profile name, bio set

GITHUB SETTINGS
[ ] Accessibility settings page visited
[ ] Hovercards / link previews turned OFF
[ ] Theme set to your preferred option
[ ] Confirmed modern GitHub Issues and Pull Request experience is working (default as of January 2026)

BROWSER & SCREEN READER
[ ] Screen reader installed and working (NVDA / JAWS / VoiceOver)
[ ] Browser chosen: Chrome, Firefox, Edge (Windows) or Safari (macOS)
[ ] Navigated to github.com with screen reader — page announces headings and landmarks
[ ] Can navigate the GitHub homepage using heading keys (H) without a mouse

DAY 2 PREP (complete before Day 2)
[ ] Visual Studio Code installed
[ ] Screen Reader Mode enabled in VS Code (Shift+Alt+F1)
[ ] Signed into GitHub in VS Code
[ ] GitHub Copilot extension installed
[ ] Copilot suggestions appear when typing in a file
```

---

## 11. Other GitHub Access Methods (Reference Only)

This workshop focuses entirely on GitHub.com in the browser and VS Code. However, you should be aware that other ways to work with GitHub exist. We list them here for your reference — we will not be teaching these in depth.

### GitHub Desktop

A graphical desktop application for managing repositories, branches, and commits without using the command line.

- Download: [desktop.github.com](https://desktop.github.com/)
- Provides a visual interface for cloning, committing, pushing, and creating PRs
- Has some screen reader support, though the web interface is generally more accessible
- A good option for those who prefer a visual GUI over the command line

### GitHub CLI (`gh`)

A command-line tool that lets you perform nearly any GitHub action directly from your terminal.

```bash
# Examples (reference only — not covered in this workshop)
gh repo clone owner/repo
gh issue create
gh pr create
gh pr review
gh pr merge
```

- Download: [cli.github.com](https://cli.github.com/)
- Excellent for automation and scripting
- Very accessible — terminal/command-line interfaces work well with screen readers
- Full documentation: [cli.github.com/manual](https://cli.github.com/manual/)

### GitHub Copilot CLI (`gh copilot`)

An extension to the GitHub CLI that brings Copilot assistance to the terminal. You can ask it to explain or suggest shell commands in plain English.

```bash
# Reference examples only
gh copilot suggest "how do I undo my last commit"
gh copilot explain "git rebase -i HEAD~3"
```

- Install: `gh extension install github/gh-copilot`
- Documentation: [docs.github.com/en/copilot/github-copilot-in-the-cli](https://docs.github.com/en/copilot/github-copilot-in-the-cli/about-github-copilot-in-the-cli)
- Particularly useful for users who prefer a terminal workflow

### Git (the version control system itself)

GitHub is a platform built on top of **Git**, which is the underlying version control system. Git runs locally on your computer via a terminal.

We are not covering Git commands in this workshop. If you want to learn Git, these are excellent starting points:

- [Git Handbook](https://guides.github.com/introduction/git-handbook/)
- [Pro Git book (free)](https://git-scm.com/book/en/v2)
- [GitHub Skills: Introduction to GitHub](https://github.com/skills/introduction-to-github)

---

## 12. Getting Help Before the Event

If you cannot complete any step in this guide before the workshop:

1. **File an issue in this repository** — describe exactly what step you are on and what is not working
2. **Join the GitHub Accessibility Discussions** — [github.com/orgs/community/discussions/categories/accessibility](https://github.com/orgs/community/discussions/categories/accessibility) — the community is helpful and welcoming
3. **Contact the event organizers** — details provided in your registration confirmation

You will not be left behind. Every setup issue we can solve before Day 1 means more time for learning on the day.

---

*Next: [Understanding GitHub's Web Structure](01-understanding-github-web-structure.md)*
*Back: [README](../README.md)*
