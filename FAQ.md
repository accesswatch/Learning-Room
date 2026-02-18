# FAQ: Frequently Asked Questions

---

## About This Guide

### Q: Is this guide only for programmers?
**A:** No! While it focuses on GitHub (which developers use), the concepts apply to anyone collaborating on projects. The guide emphasizes accessibility and inclusive language, so non-technical team members can follow too. **Start:** Chapter 1 (no coding required).

### Q: Do I need to know how to code to understand this guide?
**A:** Not for most chapters. Chapters 0-14 teach GitHub concepts without requiring code knowledge. Chapters 15-17 introduce programming concepts but explain them for beginners. **If you're non-technical:** You can skip code examples and still understand the workflow.

### Q: How long will this take?
**A:** Depends on your path:
- **Core path (Day 1 only):** 8 hours
- **Full curriculum:** 12-15 hours
- **Just the essentials:** 3-4 hours (Chapters 0, 1, 4, 5)

---

## Is This For Me?

### Q: I'm a complete beginner to GitHub. Where do I start?
**A:** Start with **Chapter 0 (Pre-Workshop Setup)** to install tools, then **Chapter 1 (Understanding GitHub Web Structure)**. Both assume zero prior knowledge.

### Q: I use GitHub at work but don't understand how to use it well. Can this help?
**A:** Yes! **Chapter 4 (Working with Issues)** and **Chapter 5 (Working with Pull Requests)** will deepen your understanding. Then jump to **Chapter 15 (Code Review)** for best practices.

### Q: I'm a maintainer of an open-source project. What should I read?
**A:** **Chapter 8 (Labels, Milestones & Projects)** → **Chapter 15 (Issue Templates)** → **Chapter 16 (Agent Forge)**. These focus on organizing projects and automating common tasks.

### Q: I'm teaching GitHub to a group. Do I need to know everything?
**A:** Yes, read the full curriculum first. Also read **FACILITATOR.md** for tips. You'll find lesson plans in **Chapter 2** and **Chapter 10** for structuring a workshop.

### Q: I use screen readers (NVDA/JAWS/VoiceOver). Is this guide accessible?
**A:** Yes! This guide was designed with accessibility in mind. Every chapter includes screen reader instructions. **Chapter 15 (Accessible Code Review)** has detailed keyboard-only workflows. Start: **Appendix B (Screen Reader Cheatsheet)** for quick commands.

### Q: I'm not a native English speaker. Can I understand this?
**A:** Yes! All technical terms are defined in **Appendix A (Glossary)**. The language is simple and direct. If anything is unclear, open an issue on GitHub or check **QUICK_REFERENCE.md** (tables are easier to scan).

---

## Getting Started

### Q: I installed Git, but I'm getting "git: command not found". What do I do?
**A:** See **TROUBLESHOOTING.md** → "Problem: Git is not installed". It has platform-specific steps (Windows, macOS, Linux).

### Q: I created a GitHub account, but I can't clone repositories. Why?
**A:** You likely need to set up authentication (SSH key or HTTPS). See **Chapter 0 (Pre-Workshop Setup)** or **TROUBLESHOOTING.md** → "Problem: Authentication fails when pushing".

### Q: Do I need to understand branching and merging before starting?
**A:** Not required! It's covered in **Chapter 5 (PRs)**. You can learn as you go. **Chapter 6 (Merge Conflicts)** explains what to do if something breaks.

---

## Issues & Pull Requests

### Q: What's the difference between an issue and a pull request?
**A:** 
- **Issue** = A problem or request (e.g., "Fix login bug")
- **Pull request** = Your solution (the code that fixes it)
- **See:** Chapter 4 vs. Chapter 5 for details

### Q: How do I know if I should open an issue or a PR?
**A:**
- **Open an issue if:** You found a bug, want to suggest a feature, or have a question
- **Open a PR if:** You already have code to fix/improve something
- **Both?** Open issue first, discuss, then open PR with your solution

### Q: My PR has merge conflicts. Am I in trouble?
**A:** No! Merge conflicts are normal. See **Chapter 6 (Merge Conflicts)** for how to resolve them easily. It's just Git's way of saying "Two people edited the same part of the file."

### Q: How long does it take to get PR feedback?
**A:** Depends on the project. Open-source projects may take days or weeks. Your company's repo might be hours. Check the project's **CONTRIBUTING.md** for estimated review time.

---

## Templates & Automation

### Q: What's an issue template and why should I care?
**A:** Templates guide people to provide the right information when they create issues. Saves time for maintainers. **See:** Chapter 16 (Issue Templates) to create one.

### Q: Can I use Copilot to help me review code?
**A:** Yes! The `@pr-review` agent does exactly this. **See:** Chapter 16 (Agent Forge) for details.

### Q: What's the `@template-builder` agent and how is it different?
**A:** It's a NEW interactive wizard that walks you through creating issue templates using AI guidance. Instead of writing YAML manually, the agent asks questions and generates the template for you. **See:** Chapter 15 (Day 2 Amplifier) or Chapter 16 (Agent Forge).

### Q: Do I need a paid GitHub Copilot subscription to use agents?
**A:** Yes, agents require GitHub Copilot. Free alternatives: Use GitHub's web interface manually (still powerful!).

---

## Accessibility & Inclusive Practices

### Q: What makes code review "accessible"?
**A:** Using keyboard shortcuts instead of mouse, testing with screen readers, writing descriptive comments. **See:** Chapter 15 (Accessible Code Review) for details.

### Q: How do I test for accessibility in GitHub?
**A:** Use screen readers (NVDA/JAWS/VoiceOver). **See:** Appendix B (Screen Reader Cheatsheet) for commands. Or use automated tools like WAVE or Axe. **See:** RESOURCES.md for links.

### Q: Why do issue templates need to be accessible?
**A:** So people using screen readers can fill them out easily. Required fields should be marked and announced. **See:** Chapter 16 (Issue Templates) for accessible template design.

### Q: Can I use this guide with a screen reader?
**A:** Yes! Every chapter has keyboard-only workflows and screen reader instructions. This guide was designed with accessibility in mind.

---

## Troubleshooting & Help

### Q: I followed the steps but my template doesn't show up on GitHub.
**A:** Check:
1. Is the file in the right location? (`.github/ISSUE_TEMPLATE/your-template.yml`)
2. Is the YAML syntax correct? (Use https://www.yamllint.com/)
3. Did you push to the `main` branch?
4. Try a hard refresh: `Ctrl+Shift+R`

**Full diagnostics:** See TROUBLESHOOTING.md → "Problem: Template not showing in GitHub"

### Q: The exercises don't make sense. What do I do?
**A:** 
1. **Reread** the prerequisites (listed at the start of each exercise)
2. **Check** the "What you should see" checkpoint after each step
3. **Look for** the "If you're stuck" troubleshooting section within the exercise
4. **Consult:** QUICK_REFERENCE.md for keyboard commands
5. **Ask:** Open an issue describing what's confusing

### Q: I'm stuck on a step and can't move forward. How do I get help?
**A:** 
1. Check **TROUBLESHOOTING.md** (may have exact answer)
2. Check **QUICK_REFERENCE.md** (commands, shortcuts)
3. Check **RESOURCES.md** (external documentation)
4. Open **GitHub Issue** with:
   - Screenshot or description of your problem
   - Which exercise and step you're on
   - What you tried

### Q: I think I found a mistake in the guide. What do I do?
**A:** Open an issue! Describe:
- Which chapter/section
- What the mistake is
- What it should say
- If possible, suggest a fix

See **CONTRIBUTING.md** for contribution guidelines.

---

## Concepts & Terminology

### Q: What's the difference between a fork and a branch?
**A:**
- **Fork** = Your complete separate copy of a repository (on GitHub)
- **Branch** = A version of the code within a repository
- **Use fork to:** Contribute to someone else's open-source project
- **Use branch to:** Work on features in your own repository

**See:** Chapter 1 for detailed explanation.

### Q: What's a "pull request"? Why is it called that?
**A:** 
- **Pull request** (PR) = You're asking the maintainer to "pull" your changes into their repository
- Literally: "Pull my changes into your project"
- Also called: **Merge request** (GitLab uses this term)

### Q: What does "merge" mean?
**A:** Combining two branches of code. After your PR is approved, it's "merged" into `main`. The changes become official.

### Q: What's YAML and why is it used for templates?
**A:** 
- **YAML** = A simple format for writing structured data
- **Why GitHub uses it:** It's human-readable (not like XML or JSON)
- **Don't panic:** Chapter 16 teaches it; you don't need to be an expert

---

## Advanced Questions

### Q: Can I contribute to this curriculum?
**A:** Yes! See **CONTRIBUTING.md** for how to submit improvements, suggest new topics, or fix issues.

### Q: I want to share this guide with my team. Can I?
**A:** Yes! The curriculum is open-source. See **LICENSE** file (if present) for usage rights. Typically you can share freely; credit the original authors.

### Q: Can I modify the guide for my organization?
**A:** Yes! You can fork this repository and customize for your needs. See **CONTRIBUTING.md** → Contributing at Scale.

### Q: What if my question isn't answered here?
**A:** 
1. Check **Appendix A (Glossary)** for term definitions
2. Search existing **GitHub Issues**
3. Open a new issue: "FAQ: [Your question]"
4. Or ask in **Discussions** section

---

## Still Stuck?

This FAQ doesn't cover your question? Try these resources in order:

1. **QUICK_REFERENCE.md** — Commands, keyboard shortcuts, file locations
2. **TROUBLESHOOTING.md** — Common problems & solutions
3. **RESOURCES.md** — External documentation and links
4. **Appendix A (Glossary)** — Term definitions
5. **Appendix B (Screen Reader Cheatsheet)** — Keyboard commands for NVDA/JAWS/VoiceOver
6. **GitHub Issues** — Search or open new issue
7. **FACILITATOR.md** — If you're leading a workshop

---

*Last updated: February 2026*  
*Have more questions? Open an issue or discussion on GitHub!*
