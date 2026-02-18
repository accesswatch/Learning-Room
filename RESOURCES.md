# Resources & Reference Materials
## Comprehensive Resource Manifest

---

## Table of Contents
- [GitHub Learning](#github-learning)
- [Accessibility & Inclusive Design](#accessibility--inclusive-design)
- [Git & Command Line](#git--command-line)
- [Code Review & Collaboration](#code-review--collaboration)
- [Agent Forge & Automation](#agent-forge--automation)
- [Issue Templates & YAML](#issue-templates--yaml)
- [Screen Readers & Accessibility Tools](#screen-readers--accessibility-tools)
- [VS Code & Development Environment](#vs-code--development-environment)

---

## GitHub Learning

### Official GitHub Documentation
- **GitHub Skills (Free Interactive Courses):** https://skills.github.com/
  - Covers: Git basics, PR workflows, Actions, Codespaces
  - Format: Interactive exercises with live feedback
  - Time: 15-30 min per skill

- **GitHub Learning Lab (Legacy):** https://lab.github.com/
  - Beginner to advanced workflows
  - Interactive lessons with feedback

- **GitHub Docs - Getting Started:** https://docs.github.com/en/get-started
  - Comprehensive reference for all GitHub features
  - Setup guides, concepts, how-tos

### GitHub-Specific Topics Covered in This Guide
| Topic | Chapter | Quick Link |
|-------|---------|-----------|
| Understanding GitHub Structure | Chapter 1 | `docs/01-understanding-github-web-structure.md` |
| Working with Issues | Chapter 4 | `docs/04-working-with-issues.md` |
| Pull Requests & Collaboration | Chapter 5 | `docs/05-working-with-pull-requests.md` |
| Merge Conflicts | Chapter 6 | `docs/06-merge-conflicts.md` |
| Labels & Milestones | Chapter 8 | `docs/08-labels-milestones-projects.md` |
| GitHub Notifications | Chapter 9 | `docs/09-notifications.md` |

---

## Accessibility & Inclusive Design

### WCAG 2.1 Standards
- **WCAG Guidelines (W3C):** https://www.w3.org/WAI/WCAG21/quickref/
  - Standard for accessible web content
  - Four principles: Perceivable, Operable, Understandable, Robust
  - Levels: A, AA (GitHub targeting AA compliance)

- **W3C Web Accessibility Initiative:** https://www.w3.org/WAI/
  - Tutorials, guides, and best practices
  - Color contrast checkers, form labeling guides

### Accessibility Tools & Checkers
- **WebAIM Contrast Checker:** https://webaim.org/articles/contrast/
  - Check if text/background colors meet WCAG AA/AAA
  - Tool: https://webaim.org/resources/contrastchecker/

- **WAVE Browser Extension:** https://wave.webaim.org/extension/
  - Highlights accessibility issues on any webpage
  - Available for Chrome, Firefox, Edge

- **Axe DevTools:** https://www.deque.com/axe/devtools/
  - Comprehensive accessibility auditing
  - Finds WCAG 2.1 violations with severity levels

- **Lighthouse (Built-in):** https://developers.google.com/web/tools/lighthouse
  - In Chrome DevTools (F12 → Lighthouse tab)
  - Includes accessibility, performance, SEO scores

### Focus on Form Accessibility
- **WebAIM: Web Form Accessibility:** https://webaim.org/articles/form/
- **MDN: HTML Form Elements:** https://developer.mozilla.org/en-US/docs/Web/HTML/Element#forms
- **Checkbox & Radio Button Accessibility:** https://www.a11y-101.com/design/checkbox

### This Guide's Accessibility Resources
| Topic | Chapter | Reference |
|-------|---------|-----------|
| Accessible Code Review Principles | Chapter 14 | `docs/14-accessible-code-review.md` |
| Accessibility Bug Templates | Chapter 15 | `docs/15-issue-templates.md` |
| Screen Reader Commands Appendix | Appendix B | `docs/appendix-b-screen-reader-cheatsheet.md` |

---

## Git & Command Line

### Interactive Git Learning
- **Visualizing Git:** https://git-school.github.io/visualizing-git/
  - Visual branch and commit diagrams
  - Interactive playground

- **Learn Git Branching:** https://learngitbranching.js.org/
  - Gamified learning with step-by-step challenges
  - Covers branching, merging, rebasing

- **Oh My Zsh (macOS/Linux):** https://ohmyz.sh/
  - Terminal enhancements with git aliases
  - Improves command-line experience

### Git Reference
- **Official Git Documentation:** https://git-scm.com/doc
- **Git Cheat Sheet:** https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf
- **Pro Git Book (Free):** https://git-scm.com/book/en/v2

### Terminal/Command Line
- **Windows PowerShell Docs:** https://docs.microsoft.com/en-us/powershell/
- **macOS Terminal Basics:** https://support.apple.com/guide/terminal/welcome/mac
- **Linux Command Guide:** https://linux.die.net/man/

---

## Code Review & Collaboration

### Code Review Best Practices
- **GitHub: Code Review Guide:** https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests
- **Chromium Code Review Standards:** https://chromium.googlesource.com/chromium/src/+/main/docs/code_reviews.md
- **Google Engineering Practices:** https://google.github.io/eng-practices/review/

### PR Review Tools & Features
- **GitHub PR Review Documentation:** https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-proposed-changes-in-a-pull-request
- **VS Code Diff Viewer:** `docs/14-accessible-code-review.md` (Chapter 14, Exercise B)

---

## Agent Forge & Automation

### GitHub Copilot Documentation
- **Copilot Official Docs:** https://docs.github.com/en/copilot
- **Copilot Pricing & Access:** https://github.com/features/copilot
- **Copilot Chat in VS Code:** https://docs.github.com/en/copilot/using-github-copilot/using-copilot-chat-in-your-ide

### Copilot Chat Agents (This Guide)
- **Agent Forge Overview:** Chapter 16 (`docs/16-agent-forge.md`)
- **Agent List:**
  1. `@daily-briefing` — Daily GitHub activity summary
  2. `@issue-tracker` — Issue management assistant
  3. `@pr-review` — Pull request reviewer
  4. `@analytics` — Repository metrics and insights
  5. `@insiders-a11y-tracker` — Accessibility issue finder
  6. `@template-builder` — Interactive template wizard (NEW)

### Prompt Engineering
- **Prompt Engineering Guide:** https://platform.openai.com/docs/guides/prompt-engineering/six-strategies-for-better-results
- **Effective Prompting:** https://github.com/dair-ai/Prompt-Engineering-Guide
- **ChatGPT Best Practices:** https://platform.openai.com/docs/guides/gpt-best-practices

---

## Issue Templates & YAML

### YAML for GitHub Templates
- **GitHub: Issue Templates Documentation:** https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests
- **YAML Syntax Guide:** https://yaml.org/spec/1.2/spec.html
- **YAML Validator:** https://www.yamllint.com/

### Template Field Reference
- **Input Fields:** Text, textarea, dropdown, checkboxes, markdown syntax
- **Validation Rules:** Required fields, placeholder text, format hints
- **Examples in This Guide:** Chapter 15 (`docs/15-issue-templates.md`)

### Template Best Practices
- **Creating Helpful Templates:** https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/about-issue-and-pull-request-templates
- **Template Design (This Guide):** Chapter 16, Day 2 Amplifier

---

## Screen Readers & Accessibility Tools

### NVDA (Windows) — Free, Open-Source
- **Official Site:** https://www.nvaccess.org/
- **User Guide:** https://www.nvaccess.org/document/toc/
- **Keyboard Commands:** https://www.nvaccess.org/files/nvda/documentation/userGuide.html#toc2
- **Download:** https://www.nvaccess.org/download/
- **Cost:** Free (donations welcome)

### JAWS (Windows) — Commercial, Most Feature-Rich
- **Official Site:** https://www.freedomscientific.com/products/software/jaws/
- **User Guide:** https://www.freedomscientific.com/training/
- **Keyboard Reference:** https://www.freedomscientific.com/SurfsUp/StartGuide.html
- **Download Trial:** https://www.freedomscientific.com/products/software/jaws/
- **Cost:** ~$90/year personal, bulk discounts for organizations

### VoiceOver (macOS/iOS) — Built-in
- **Official Documentation:** https://www.apple.com/accessibility/voiceover/
- **Getting Started Guide:** https://www.apple.com/accessibility/voiceover/
- **Web Content Guide:** https://www.apple.com/accessibility/
- **Cost:** Built into macOS/iOS (included)

### Narrator (Windows) — Built-in
- **Microsoft Documentation:** https://support.microsoft.com/en-us/windows/complete-guide-to-narrator-8d5010a7-776a-1119-a7f0-27f24acf3083
- **Keyboard Reference:** https://support.microsoft.com/en-us/windows/narrator-keyboard-commands-and-touch-gestures-004f71a5-7951-b079-e84e-ec8f00935eb0
- **Cost:** Built into Windows (included)

### Accessibility Testing Resources
- **Screen Reader Testing Guide:** `docs/appendix-b-screen-reader-cheatsheet.md`
- **This Guide's Accessibility Chapter:** Chapter 14 (`docs/14-accessible-code-review.md`)
- **Testing Checklist:** `QUICK_REFERENCE.md` (accessibility section)

---

## VS Code & Development Environment

### VS Code Official Resources
- **VS Code Homepage:** https://code.visualstudio.com/
- **Getting Started Guide:** https://code.visualstudio.com/docs/introvideos/basics
- **Accessibility Documentation:** https://code.visualstudio.com/docs/editor/accessibility
- **Keyboard Shortcuts:** https://code.visualstudio.com/docs/getstarted/keybindings

### Essential Extensions for This Guide
| Extension | Purpose | Link |
|-----------|---------|------|
| GitHub Copilot | AI-powered code assistance | https://marketplace.visualstudio.com/items?itemName=GitHub.copilot |
| GitHub Copilot Chat | Conversational AI in VS Code | https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat |
| GitHub Pull Requests and Issues | Integrated PR/Issue management | https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github |
| GitLens | Enhanced git visualization | https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens |
| YAML Support | YAML validation for templates | https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml |

### Accessible Diff Viewer (VS Code)
- **Press F7** to enable accessible diff view for PR reviews
- **Keyboard Navigation:** Use arrow keys to move between changes
- **Described in Chapter:** 14, Exercise B (`docs/14-accessible-code-review.md`)

### VS Code Settings for Accessibility
- **Accessible View (Alt+F2):** High-contrast, large-text mode
- **Editor Font Size:** Settings → Search "Font Size" → Adjust (recommended 14-16pt)
- **Color Theme:** Preferences → Color Theme → Choose high-contrast option
- **Full Guide:** https://code.visualstudio.com/docs/editor/accessibility

---

## Additional Learning Pathways

### By Role
| Role | Start Here | Next |
|------|-----------|------|
| Contributor | Ch 0 (Setup) | Ch 4 (Issues) → Ch 5 (PRs) → Ch 15 (Review) |
| Maintainer | Ch 8 (Labels) | Ch 16 (Templates) → Ch 17 (Agents) |
| Facilitator | Ch 2 (Day 1 Agenda) in docs | `FACILITATOR.md` |
| Accessibility Advocate | Ch 15 (Review) | `docs/appendix-b-screen-reader-cheatsheet.md`, Ch 16 (Templates) |

### By Time Available
| Time | Path |
|------|------|
| 30 minutes | Chapter 0 (Setup) → Chapter 1 (Structure) |
| 1 hour | Above + Chapter 4 (Issues) |
| 2 hours | Above + Chapter 5 (PRs) + Chapter 3 (Navigation) |
| 4+ hours | All core chapters (0-10) + choose 1 advanced topic (15-17) |

---

## Community & Support

### Where to Ask Questions
1. **GitHub Discussions:** Open forums (not GitHub project-specific)
2. **GitHub Issues:** Bug reports and feature requests
3. **Stack Overflow:** Search `[github]` tag for common questions
4. **Reddit r/github:** Community discussion
5. **This Guide's Troubleshooting:** `TROUBLESHOOTING.md`

### Contributing to This Guide
- **How to Contribute:** `CONTRIBUTING.md`
- **Code of Conduct:** `CODE_OF_CONDUCT.md`
- **Open Issues:** https://github.com/[REPO]/issues
- **Discussion Forum:** https://github.com/[REPO]/discussions

---

## Glossary & Terminology

- **See `docs/appendix-a-glossary.md`** for definitions of all terms used in this guide
- **Quick definitions in Chapter 1** for GitHub-specific concepts

---

## Tips for Using This Manifest

- **Stuck on a topic?** Find the resource link above, then come back to the chapter
- **Want deeper learning?** Official documentation links provide comprehensive coverage
- **Need accessibility help?** See "Screen Readers & Accessibility Tools" section
- **Using an agent?** Check "Agent Forge" section for agent-specific docs
- **Lost in the curriculum?** Use table "By Role" or "By Time Available" above

---

*Last updated: February 2026*  
*For latest versions and additional resources, check the GitHub repository*
