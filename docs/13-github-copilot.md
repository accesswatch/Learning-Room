# GitHub Copilot
## AI-Powered Code Assistance in VS Code

> **Day 2, Block 2-3 Material**
>
> This guide covers GitHub Copilot: inline code suggestions, Copilot Chat (conversational assistance), custom instructions vs custom agents, effective prompting for non-code contributions, and using Accessible View to read AI-generated responses.
>
> **Prerequisites:** [VS Code Setup & Accessibility Basics](11-vscode-basics.md), [Git & Source Control in VS Code](12-git-source-control.md)

---

## Table of Contents

1. [What is GitHub Copilot](#1-what-is-github-copilot)
2. [Installing GitHub Copilot](#2-installing-github-copilot)
3. [Inline Suggestions — Ghost Text Completions](#3-inline-suggestions--ghost-text-completions)
4. [GitHub Copilot Chat — Conversational Assistance](#4-github-copilot-chat--conversational-assistance)
5. [Effective Prompting for Documentation Work](#5-effective-prompting-for-documentation-work)
6. [Custom Instructions vs Custom Agents](#6-custom-instructions-vs-custom-agents)
7. [Using Accessible View with Copilot Responses](#7-using-accessible-view-with-copilot-responses)
8. [Keyboard Shortcuts Reference](#8-keyboard-shortcuts-reference)

---

## 1. What is GitHub Copilot

GitHub Copilot is an AI pair programmer that suggests code and text completions as you type. It can:

- Complete lines of code or documentation
- Generate entire functions or sections of text from comments
- Answer questions about code in your workspace
- Explain complex code in plain language
- Draft documentation, issue responses, and commit messages
- Search for files and symbols across your workspace

**For this workshop:** Copilot helps with Markdown documentation, issue triage, PR descriptions, and commit messages — not just code.

**Copilot Free tier:** Available for all GitHub users. Provides access to inline suggestions and Copilot Chat with usage limits. No payment required for this workshop.

**Screen reader support:** Copilot is fully accessible with screen readers. Suggestions are announced via ARIA live regions, and Accessible View provides complete access to Chat responses.

---

## 2. Installing GitHub Copilot

### Installation Steps

1. Open Extensions sidebar: `Ctrl+Shift+X`
2. Search for "GitHub Copilot"
3. Find "GitHub Copilot" (publisher: GitHub)
4. Press `Enter` to open the extension detail page
5. `Tab` to "Install" button → press `Enter`
6. Wait for installation to complete

**Additional extension:** "GitHub Copilot Chat" may install automatically. If not, install it separately (same process).

### Signing In

After installation:

1. VS Code prompts: "Sign in to use GitHub Copilot"
2. Navigate to the notification or click the Copilot icon in the status bar
3. Select "Sign in to GitHub"
4. Your browser opens for GitHub authentication
5. Authorize the Copilot extension
6. Return to VS Code

**Verify activation:**
- Bottom-right status bar shows Copilot icon (looks like `><`)
- Icon should be active (not grayed out)
- If grayed out, click it to sign in

### Checking Subscription Status

**Command Palette:**
1. `Ctrl+Shift+P`
2. Type "Copilot: Check Status"
3. Select it to see your subscription tier (Free, Pro, Enterprise)

**Free tier includes:**
- Completions and multi-line suggestions
- Copilot Chat
- Limited monthly usage (usually sufficient for documentation work)

---

## 3. Inline Suggestions — Ghost Text Completions

Copilot suggests completions as you type, displayed as gray "ghost text" after your cursor. In screen reader mode, VS Code announces suggestions rather than showing them visually.

### How Inline Suggestions Work

**While typing:**
1. Copilot analyzes your context (file content, cursor position, nearby files)
2. Generates a suggestion
3. Displays it as ghost text

**Screen reader announcement:**
- NVDA/JAWS: "Suggestion available" (or reads the suggestion text depending on verbosity settings)
- VoiceOver: Announces suggestions in accessible form

### Accepting Suggestions

| Action | Shortcut |
|--------|----------|
| Accept entire suggestion | `Tab` |
| Reject suggestion | `Escape` |
| Accept one word at a time | `Ctrl+Right Arrow` |
| Show next alternative suggestion | `Alt+]` |
| Show previous alternative suggestion | `Alt+[` |
| Open full suggestion list | `Ctrl+Enter` |

**Accepting word-by-word (`Ctrl+Right Arrow`) is particularly useful when:**
- The suggestion starts correctly but you want to finish differently
- You want to review the suggestion incrementally
- You're learning and want to see how Copilot structures responses

### Reading Suggestions with Screen Readers

**If suggestions are too frequent or intrusive:**

**NVDA:**
1. NVDA Menu → Preferences → Settings → Presentation
2. Find "Report dynamic content changes"
3. Reduce verbosity level or set specific delays

**JAWS:**
1. Settings Center → HTML/PDF/Accessibility
2. Adjust "Auto Forms Mode" and "ARIA Live Region" settings

**VoiceOver:**
1. VoiceOver Utility → Verbosity
2. Reduce "Announcements" level

**Alternative: Use Accessible View**
Press `Alt+F2` when a suggestion appears to read it in the Accessible View (full text, no streaming).

### Prompting Through Comments

Copilot reads inline comments as instructions. For Markdown files:

```markdown
<!-- Write a step-by-step guide for screen reader users on how to create a GitHub issue -->
```

Type this comment, press `Enter`, and Copilot drafts content based on your instruction. You review, edit, and refine.

**Example prompts for this workshop:**

```markdown
<!-- Explain how to navigate the GitHub Issues list with NVDA -->

<!-- Create a checklist for accessible Markdown documentation -->

<!-- Write alt text for a screenshot showing the GitHub PR review interface -->

<!-- Draft a commit message for fixing heading hierarchy in GUIDE.md -->
```

### Disabling Inline Suggestions

If suggestions are distracting:

**Temporarily (current file):**
- Click the Copilot icon in status bar → "Disable Completions for [language]"

**Permanently:**
- Settings (`Ctrl+,`) → search "Copilot enable"
- Uncheck "Enable Inline Suggestions"

---

## 4. GitHub Copilot Chat — Conversational Assistance

Copilot Chat is a full conversation interface where you ask questions, request explanations, and have content drafted.

### Opening Copilot Chat

**Primary panel:** `Ctrl+Shift+I`

Opens the Chat panel on the right side of VS Code.

**Inline chat (in-file):** `Ctrl+I`

Opens a chat prompt directly in the editor, anchored to your cursor. Results appear inline. Best for file-specific edits.

**Quick Chat (floating):** `Ctrl+Shift+Alt+I` (Windows) / `Cmd+Shift+I` (macOS)

Opens a floating chat dialog that doesn't take up sidebar space.

### Chat Interface Structure

**Panel layout (top to bottom):**

1. **Chat input field** (multi-line text area)
   - Type your prompt here
   - Press `Ctrl+Enter` or `Enter` to send

2. **Model selector dropdown**
   - Choose which AI model to use (GPT-4, Claude, etc.)
   - Some models better for code, others for prose

3. **Conversation history**
   - Shows your previous prompts and Copilot's responses
   - Navigate with `Up/Down Arrow`
   - Each message is a separate element

4. **Action buttons**
   - "Clear Chat" — start a new conversation
   - "View in Editor" — open response in a new file

### Screen Reader Navigation in Chat

**NVDA/JAWS:**
- Chat input is a web-based text field
- Switch to Forms Mode (`Enter` or automatic when focused)
- Type your prompt
- Press `Ctrl+Enter` to send
- Response appears in a live region (announced as it streams in)
- For complete reading: press `Alt+F2` for Accessible View

**VoiceOver:**
- `VO+Tab` to navigate to chat input
- `VO+Shift+Down` to interact
- Type prompt, `Return` to send
- `VO+Escape` to stop interacting
- Navigate down to response area
- For complete reading: `Alt+F2` for Accessible View

### What to Ask Copilot Chat

**For this workshop (non-coding examples):**

| Goal | Example Prompt |
|------|----------------|
| Understand a file | `Explain what @11-vscode-basics.md covers in plain language` |
| Improve documentation | `This section is unclear. Rewrite it for a first-time contributor using a screen reader: [paste text]` |
| Check tone | `Review this PR description for tone. Is it clear, respectful, and helpful? Suggest improvements.` |
| Draft content | `Write a section on keyboard navigation in VS Code for screen reader users` |
| Explain an error | `I got this error when trying to commit: [paste error]. What does it mean and how do I fix it?` |
| Generate alt text | `Write alt text for this image: [describe what's in the image]` |
| Create checklist | `Create an accessibility review checklist for Markdown documentation` |
| Review for accessibility | `Check this Markdown for accessibility issues: [paste content]` |

### Using @ Mentions in Chat

**@ symbols let you provide context to Copilot:**

| Mention | What It Does |
|---------|-------------|
| `@workspace` | Searches your entire workspace for context |
| `@filename.md` | References a specific file |
| `#file` | Lists files to select from |
| `#selection` | References your currently selected text |
| `#terminalLastCommand` | References the last terminal command and output |

**Example prompts with context:**

```
Explain what @README.md covers for a new contributor

Review #selection for accessibility issues

Search @workspace for all references to "screen reader mode"

What does this error mean? #terminalLastCommand
```

### Using Slash Commands

Type `/` in Copilot Chat to see available commands:

| Command | What It Does |
|---------|-------------|
| `/explain` | Explains selected code or text |
| `/fix` | Suggests fixes for problems in selected code |
| `/tests` | Generates tests (for code files) |
| `/help` | Shows all available commands |
| `/clear` | Clears chat history |

**Example:**
1. Select a block of complex Markdown
2. Open Chat: `Ctrl+Shift+I`
3. Type `/explain`
4. Copilot explains the structure and purpose

---

## 5. Effective Prompting for Documentation Work

Copilot works best with clear, specific prompts. The more context you provide, the better the response.

### Anatomy of a Good Prompt

**Bad prompt:**
```
Write about accessibility
```

**Good prompt:**
```
Write a 3-paragraph section explaining how screen reader users can navigate the VS Code Explorer sidebar. Include keyboard shortcuts for NVDA and JAWS. Assume the reader has never used VS Code before. Use clear headings and bullet points.
```

**What makes it good:**
1. **Specific scope:** "3-paragraph section"
2. **Clear topic:** "navigate the VS Code Explorer sidebar"
3. **Target audience:** "screen reader users" who "never used VS Code"
4. **Required details:** "keyboard shortcuts for NVDA and JAWS"
5. **Format guidance:** "headings and bullet points"

### Prompting Patterns for This Workshop

**Pattern 1: Contextual Rewrite**

```
This section is too technical for beginners. Rewrite it in plain language:

[paste existing text]

Target audience: Screen reader users trying VS Code for the first time
```

**Pattern 2: Generate with Constraints**

```
Write a step-by-step guide for creating a GitHub issue using only keyboard navigation. Include:
- NVDA screen reader announcements
- Exact keyboard shortcuts
- What to do if the form field is not announced correctly
Format as a numbered list
```

**Pattern 3: Review and Improve**

```
Review this PR description for:
1. Clarity for maintainers
2. Respect and positive tone
3. Whether it links to the related issue
4. If it explains WHY the change matters

Here's the description:
[paste your PR description]
```

**Pattern 4: Accessibility Audit**

```
Check this Markdown for accessibility problems:
- Heading hierarchy (H1 → H2 → H3, no skips)
- Link text (no "click here" or bare URLs)
- Alt text for images
- List structure

[paste Markdown content]
```

**Pattern 5: Draft from Outline**

```
Write a section based on this outline:

## Timeline View — File History
- What Timeline shows
- How to open it (keyboard)
- How screen readers announce each commit
- How to view a specific commit's changes

Write for screen reader users. Use H3 subheadings. Include a table for keyboard shortcuts.
```

### Iterating on Responses

Copilot's first response is a draft. Refine it:

**Follow-up prompts:**

```
Make it shorter — reduce to 5 bullet points

Add more detail about what NVDA announces at each step

Rewrite this in a more friendly tone

Add a "Common Mistakes" section at the end

Format this as a table instead of a bulleted list
```

Copilot remembers the conversation context — just say what to change.

---

## 6. Custom Instructions vs Custom Agents

Two distinct tools shape how Copilot behaves. Understanding the difference is critical for working with Agent Forge (see [Chapter 16: Agent Forge](16-agent-forge.md)).

### Custom Instructions

**File:** `.github/copilot-instructions.md`

**Purpose:** Always-on background guidance for every Copilot interaction.

**What they do:**
- Apply to all code suggestions automatically
- Set project-wide standards
- Influence tone and style
- Provide context about your project's conventions

**Example `.github/copilot-instructions.md`:**

```markdown
# Copilot Instructions for agent-forge

## Accessibility Standards
- Include semantic HTML elements in generated markup
- Add ARIA labels to interactive components when no visible text is present
- Ensure keyboard navigation patterns are implemented for custom widgets

## Documentation Style
- Write for screen reader users first
- Include keyboard shortcuts for NVDA, JAWS, and VoiceOver
- Use active voice and imperative mood ("Press Ctrl+G" not "You can press Ctrl+G")
- Structure content with clear headings (H2 for sections, H3 for subsections)

## Commit Message Format
- Follow conventional commits: `type: description`
- Types: feat, fix, docs, style, refactor, test, chore
- Reference issues: "Fixes #123"

## Tone
- Friendly but professional
- Direct and actionable
- Assume readers are competent but may be new to this specific tool
```

**When active:** Every time Copilot generates a suggestion (inline or in Chat)

**You never have to ask for these — Copilot simply follows them.**

### Custom Agents

**Files:** `.github/agents/[name].agent.md`

**Purpose:** On-demand, focused workflows that you deliberately invoke.

**What they do:**
- Perform specific, repeatable tasks
- Can access specific tools (GitHub API, file system, terminal)
- Generate structured output (reports, reviews, analysis)
- Execute multi-step workflows

**Example agent names:**
- `@daily-briefing` — Summarize repository activity
- `@issue-tracker` — Find and prioritize issues
- `@pr-review` — Generate PR review documentation
- `@analytics` — Team contribution metrics
- `@insiders-a11y-tracker` — Monitor accessibility changes

**When active:** Only when you type `@agent-name` in Copilot Chat

See [Chapter 16: Agent Forge](16-agent-forge.md) for complete agent documentation.

### Comparison Table

| | Custom Instructions | Custom Agent |
|---|---|---|
| **When active** | Background — every interaction | On-demand — you type `@agent-name` |
| **Defined in** | `.github/copilot-instructions.md` | `.github/agents/[name].agent.md` |
| **Tool access** | Standard Copilot tools | Can restrict or grant specific permissions |
| **Best for** | Broad coding standards and preferences | Focused, repeatable, specialized tasks |
| **Requires invocation** | No — always on | Yes — explicit trigger |

### Using Both Together

**Custom instructions** ensure Copilot follows your accessibility standards on every suggestion.

**Custom agents** handle specific workflows like auditing, issue tracking, or automated remediation.

**Example workflow:**
1. Your `.github/copilot-instructions.md` says: "Always check heading hierarchy in Markdown"
2. You invoke `@insiders-a11y-tracker` to scan recent changes
3. The agent finds a heading skip (H1 → H3)
4. You ask Copilot Chat to fix it: "Fix the heading hierarchy in this file"
5. Copilot's fix follows your custom instructions (uses semantic HTML, adds ARIA where needed)

**Both work together — instructions guide every response, agents automate specific workflows.**

---

## 7. Using Accessible View with Copilot Responses

Copilot Chat responses stream in token by token. This is visually nice but can fragment screen reader announcements. **Accessible View** provides complete, structured access to generated content.

### Why Use Accessible View for Copilot

**Without Accessible View:**
- Responses announced in fragments as tokens arrive
- Live region updates may interrupt or overlap
- Difficult to re-read specific parts
- Context can be lost in streaming

**With Accessible View (`Alt+F2`):**
- Full complete response in a readable pane
- Navigate with `Up/Down Arrow` at your own pace
- Code blocks properly formatted
- Headings and lists structured
- No interruptions or live region noise

### Recommended Workflow

**Every time you ask Copilot something:**

1. Type your prompt in Chat input
2. Press `Ctrl+Enter` to send
3. Wait for response to finish (watch for typing indicator to stop)
4. Press `Alt+F2` to open Accessible View
5. Read the complete response with `Arrow` keys
6. Press `Escape` to close Accessible View and return to Chat

**Benefits:**
- You control the reading pace
- You can re-read sections easily
- Code blocks and lists are properly structured
- Headings are announced correctly

### Accessible View for Inline Suggestions

**When a suggestion appears:**

1. Don't accept it immediately
2. Press `Alt+F2`
3. Accessible View shows: "Suggestion: [full text of the suggestion]"
4. Read it completely
5. Press `Escape`
6. Press `Tab` to accept (or `Escape` to reject)

**This is especially useful for multi-line suggestions where the ghost text is hard to review.**

### Code Blocks in Accessible View

When Copilot suggests code or Markdown:

**In Accessible View:**
- Code blocks are in `<pre>` elements
- Screen readers announce "code block" or "pre-formatted text"
- Each line is on its own line (not run together)
- Indentation is preserved

**NVDA/JAWS:** Use `Arrow` keys to read line by line. Use `Ctrl+Home` to jump to the start.

**VoiceOver:** Interact with the code block (`VO+Shift+Down`) to read each line with proper structure.

---

## 8. Keyboard Shortcuts Reference

### Copilot Inline Suggestions

| Action | Windows/Linux | macOS |
|--------|---------------|-------|
| Accept suggestion | `Tab` | `Tab` |
| Reject suggestion | `Escape` | `Escape` |
| Accept word-by-word | `Ctrl+Right Arrow` | `Cmd+Right Arrow` |
| Next suggestion | `Alt+]` | `Option+]` |
| Previous suggestion | `Alt+[` | `Option+[` |
| Open suggestions list | `Ctrl+Enter` | `Cmd+Enter` |

### Copilot Chat

| Action | Windows/Linux | macOS |
|--------|---------------|-------|
| Open Chat panel | `Ctrl+Shift+I` | `Cmd+Shift+I` |
| Inline chat (in-file) | `Ctrl+I` | `Cmd+I` |
| Quick chat (floating) | `Ctrl+Shift+Alt+I` | `Cmd+Shift+Ctrl+I` |
| Send message | `Ctrl+Enter` | `Cmd+Enter` |
| Clear chat | `Ctrl+L` | `Cmd+L` |

### Accessibility

| Action | Windows/Linux | macOS |
|--------|---------------|-------|
| Open Accessible View | `Alt+F2` | `Option+F2` |
| Open Accessible Help | `Alt+H` | `Option+H` |
| Close Accessible View | `Escape` | `Escape` |

### VS Code General (Quick Reference)

| Action | Windows/Linux | macOS |
|--------|---------------|-------|
| Command Palette | `Ctrl+Shift+P` | `Cmd+Shift+P` |
| Go to file | `Ctrl+P` | `Cmd+P` |
| Find in file | `Ctrl+F` | `Cmd+F` |
| Settings | `Ctrl+,` | `Cmd+,` |
| Source Control | `Ctrl+Shift+G` | `Cmd+Shift+G` |
| Explorer | `Ctrl+Shift+E` | `Cmd+Shift+E` |
| Terminal | `Ctrl+Backtick` | `Ctrl+Backtick` |

**Complete keyboard reference:** See [Appendix F: VS Code Accessibility Reference](appendix-f-vscode-accessibility-reference.md)

---

## Troubleshooting

### Copilot Not Suggesting Anything

**Issue:** No suggestions appear as you type.

**Solutions:**
1. Check Copilot is active: status bar icon should not be grayed out
2. Click the Copilot icon → verify "Completions enabled"
3. Check subscription status: `Ctrl+Shift+P` → "Copilot: Check Status"
4. Restart VS Code
5. Sign out and sign back in: `Ctrl+Shift+P` → "Copilot: Sign Out"

### Suggestions Are Too Frequent/Distracting

**Issue:** Constant interruptions from suggestions.

**Solutions:**
1. Use word-by-word acceptance: `Ctrl+Right Arrow`
2. Reduce screen reader verbosity (see Section 3)
3. Use Accessible View (`Alt+F2`) to review suggestions without live announcements
4. Disable inline suggestions temporarily: Copilot icon → "Disable Completions"

### Chat Responses Not Announced

**Issue:** Screen reader silent when Copilot responds.

**Solutions:**
1. Wait for response to complete, then press `Alt+F2` for Accessible View
2. Check ARIA live region settings in your screen reader
3. Navigate manually to the response area with `Tab` or `Arrow` keys
4. Use Quick Chat (`Ctrl+Shift+Alt+I`) instead of panel chat

### "Copilot Subscription Required"

**Issue:** Extension installed but asks for subscription.

**Solutions:**
1. Sign in to GitHub: Copilot icon → "Sign in"
2. Verify GitHub account has Copilot access (free tier or paid)
3. Check [github.com/settings/copilot](https://github.com/settings/copilot) for subscription status
4. Free tier users: ensure you haven't exceeded monthly limits

---

*Next: [Accessible Code Review](14-accessible-code-review.md)*
*Back: [GitHub Pull Requests Extension](12-github-pull-requests-extension.md)*
*Related: [VS Code Setup & Accessibility Basics](11-vscode-basics.md) | [Appendix F: VS Code Accessibility Reference](appendix-f-vscode-accessibility-reference.md)*
