# Appendix E: Advanced GitHub Features
## Codespaces, GitHub Pages, Profile Customization, and More

> This appendix covers optional GitHub features that enhance your workflow but aren't required for basic contribution. Explore these as you become more comfortable with GitHub.

---

## GitHub Codespaces

### What Is Codespaces?

GitHub Codespaces is a cloud-based development environment that runs entirely in your browser (or VS Code). Think of it as VS Code in the cloud with all your project dependencies pre-installed.

**The value proposition:**
- No local setup required
- Works from any computer with a browser
- Pre-configured environments (project maintainers can define the setup)
- Consistent environment for all contributors
- Accessible from tablets or low-powered devices

### When to Use Codespaces

**Good use cases:**
- Testing a project quickly without installing dependencies
- Contributing from a borrowed or public computer
- Working on projects with complex setup (databases, Docker, etc.)
- Your local machine lacks the resources to run the project

**Not ideal for:**
- Projects you work on daily (local setup is faster)
- Offline work (requires internet connection)
- Extremely large repositories (can be slow to load)

### Starting a Codespace

1. Navigate to any GitHub repository
2. Select the green **"Code"** button
3. Select the **"Codespaces"** tab
4. Select **"Create codespace on main"** (or choose a branch)

GitHub spins up a virtual machine with VS Code, clones the repo, and opens it in your browser.

**Screen reader navigation:**
- Codespaces runs a full VS Code instance—all VS Code accessibility features apply
- Press `Shift+Alt+F1` to toggle screen reader mode
- Use the same keyboard shortcuts as desktop VS Code
- Terminal, editor, and sidebar are all accessible

### Codespaces Accessibility

**Good news:** Codespaces is built on VS Code, which has excellent screen reader support.

**Potential challenges:**
- Browser-based terminals can sometimes have slight accessibility differences from native terminals
- Audio cues and notifications work the same as desktop VS Code
- Some extensions may behave differently in the browser

**Recommendation:** Try Codespaces for a simple project first to get comfortable before using it for critical work.

### Codespaces Limits

GitHub provides a monthly allowance of free Codespaces hours based on your account type:

- **Free accounts:** 120 core-hours/month, 15 GB storage
- **Pro accounts:** 180 core-hours/month, 20 GB storage
- **Deeper use:** Requires a paid plan

Core-hours = hours × number of CPU cores. A 2-core machine for 60 hours = 120 core-hours.

**Tip:** Stop your Codespace when not using it. GitHub auto-stops after 30 minutes of inactivity by default.

### Codespaces vs Local Development

| Factor | Local Development | Codespaces |
|--------|-------------------|------------|
| Setup time | Can take hours | Minutes (often pre-configured) |
| Performance | Depends on your machine | Depends on instance size |
| Accessibility | Native screen reader support | Browser-based (excellent but not identical) |
| Offline work | ✅ Yes | ❌ No |
| Cost | Free (uses your machine) | Free tier or paid |
| Portability | Tied to one machine | Access from anywhere |

**Bottom line:** Codespaces is a powerful option, especially for quick contributions or trying out new projects. For daily development on projects you know well, local setup is often faster and more flexible.

---

## GitHub Pages

### What Is GitHub Pages?

GitHub Pages is a free static site hosting service that turns a GitHub repository into a live website. It's perfect for:

- **Project documentation** — host your docs alongside your code
- **Personal portfolio** — showcase your work at `username.github.io`
- **Blogs** — using static site generators like Jekyll, Hugo, or Eleventy
- **Demo sites** — let users try your project without running it locally

**Key constraint:** Static sites only. No server-side code (PHP, Python, Node.js servers). Only HTML, CSS, JavaScript.

### Types of GitHub Pages Sites

**1. User/Organization site:** `username.github.io`
   - Create a repo named exactly `username.github.io` (replace `username` with your GitHub username)
   - Push an `index.html` file to the main branch
   - Your site appears at `https://username.github.io`

**2. Project site:** `username.github.io/repo-name`
   - Any repository can have a Pages site
   - Enable Pages in Settings → Pages
   - Choose a branch and folder (`main` branch, `/docs` folder is common)
   - Your site appears at `https://username.github.io/repo-name`

### Setting Up GitHub Pages

**Method 1: Basic HTML Site**

1. Create a repository (or use an existing one)
2. Add an `index.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My GitHub Pages Site</title>
</head>
<body>
    <h1>Welcome to My Project</h1>
    <p>This is a GitHub Pages site.</p>
</body>
</html>
```

3. Navigate to **Settings → Pages**
4. Under "Branch," select `main` and `/ (root)` or `/docs`
5. Select **Save**

GitHub builds and deploys your site within a few minutes. The URL appears in the Pages settings.

**Method 2: Using Jekyll (Built-in)**

GitHub Pages has built-in support for Jekyll, a static site generator.

1. Add a `_config.yml` file to your repo:

```yaml
title: My Project Documentation
description: An accessible guide to using MyProject
theme: jekyll-theme-minimal
```

2. Create a `README.md` or `index.md` — Jekyll converts Markdown to HTML automatically
3. Enable Pages in Settings (same as above)

Jekyll themes provide pre-built layouts. Browse themes at [pages.github.com/themes/](https://pages.github.com/themes/).

### Custom Domains

You can use your own domain instead of `username.github.io`:

1. Buy a domain from any registrar (Namecheap, Google Domains, etc.)
2. In your repo's Settings → Pages, add your custom domain
3. Configure DNS records at your registrar (GitHub provides instructions)
4. GitHub automatically provisions an SSL certificate (HTTPS)

### GitHub Pages Accessibility

Since you control the HTML/CSS, accessibility is entirely up to you. Best practices:

- Use semantic HTML (`<nav>`, `<main>`, `<article>`)
- Provide alt text for all images
- Ensure sufficient color contrast
- Test with a screen reader
- Use headings hierarchically (`<h1>` → `<h2>` → `<h3>`)

Many Jekyll themes have accessibility built in. Always test before assuming.

### When Not to Use GitHub Pages

- **You need a database** — Pages serve static files only
- **You need server-side logic** — no PHP, Python, Ruby backends
- **You need authentication** — no built-in login system
- **High-traffic production apps** — Pages is best for documentation and small sites

For dynamic apps, use Vercel, Netlify, Render, or a traditional web host.

---

## Profile Customization

### The Special Profile README

GitHub has a hidden feature: if you create a repository named exactly **your-username/your-username** (e.g., `janesmith/janesmith`), the README in that repo appears on your GitHub profile page.

**This is your profile README.** It's a custom introduction visible to anyone who visits your profile.

### Creating Your Profile README

1. Create a **new repository**
2. Name it exactly `your-username` (match your GitHub username exactly, case-sensitive)
3. Make it **public**
4. Initialize with a README
5. Edit the README with whatever you want to show on your profile

**What to include:**

- **Introduction:** Who you are, what you work on
- **Current focus:** What projects or technologies you're learning
- **Skills:** Languages, frameworks, tools (optional)
- **How to reach you:** Email, LinkedIn, personal site
- **Fun facts:** Hobbies, interests (optional—keeps it human)

**Example profile README:**

```markdown
# Hi, I'm Jane Smith 👋

I'm an accessibility advocate and open source contributor focused on making the web more inclusive.

## 🔭 Current focus
- Contributing to NVDA documentation
- Building accessible React components
- Learning TypeScript

## 🌱 Skills
- JavaScript, Python, HTML/CSS
- Screen reader testing (NVDA, JAWS, VoiceOver)
- Git, GitHub, GitHub Actions

## 📫 Get in touch
- Email: jane@example.com
- LinkedIn: [linkedin.com/in/janesmith](https://linkedin.com/in/janesmith)

## ⚡ Fun fact
I've been using screen readers for 8 years and believe accessible design is better design for everyone.
```

### Profile README Best Practices

✅ **Keep it concise** — visitors skim, not read  
✅ **Update occasionally** — a README from 2019 looks stale  
✅ **Be authentic** — people connect with real humans, not buzzwords  
✅ **Include links** — make it easy to learn more or get in touch  

❌ **Avoid excessive badges** — 50 skill badges is visual clutter and screen reader noise  
❌ **Skip auto-generated stats** — "commits per day" widgets are often inaccessible  
❌ **Don't overthink it** — a simple paragraph is better than nothing  

### Screen Reader Considerations

- **Use headings** (`##`) for structure
- **Provide alt text** for any images: `![Description of image](url)`
- **Avoid ASCII art** — screen readers read it character by character (annoying)
- **Test your README** with a screen reader before publishing

### Other Profile Customizations

**Pinned repositories (up to 6):**

- Highlight your best work on your profile
- Navigate to your profile → Select "Customize your pins"
- Choose which repos appear first

**Contribution graph:**

- Shows your GitHub activity over the past year
- Green squares indicate days with commits, PRs, issues, etc.
- Cannot be customized but reflects consistent contribution

**Status:**

- Set a temporary status message (e.g., "🏖️ On vacation until March 15")
- Navigate to your profile → Select the smile icon → Set status

---

## GitHub Sponsors (Supporting Open Source)

### What Is GitHub Sponsors?

GitHub Sponsors lets you financially support developers and projects you depend on. It's like Patreon for open source.

**How it works:**
- Developers/projects create a Sponsors profile
- You choose a monthly sponsorship tier ($5, $10, $25/month, etc.)
- Your payment goes directly to the developer (GitHub takes no fees)

### Why Sponsor?

- **Sustainability:** Many open source maintainers volunteer their time. Sponsorships help them keep projects alive.
- **Gratitude:** If a project saved you hours of work, sponsorship is a way to say thanks.
- **Priority support:** Some maintainers offer sponsor-only Discord access, early releases, or prioritized bug fixes.

### How to Sponsor

1. Navigate to a user or repository's GitHub page
2. Look for the **"Sponsor"** button (heart icon)
3. Choose a tier or custom amount
4. Select payment method (credit card or PayPal)
5. GitHub sends a receipt; your sponsorship appears on your profile (optionally publicly)

**Screen reader navigation:**
- The Sponsor button appears near the profile photo or repo name
- Press `B` to cycle through buttons on the page until you hear "Sponsor"

### Can I Receive Sponsorships?

Yes! If you maintain an open source project or contribute regularly:

1. Navigate to [github.com/sponsors](https://github.com/sponsors)
2. Select "Join the waitlist" or "Set up sponsors"
3. Connect a payment method (Stripe or bank account)
4. Create sponsor tiers with descriptions
5. Promote your Sponsors page to your audience

Many accessibility advocates successfully use Sponsors to fund their work improving assistive technology and inclusive design.

---

## GitHub Discussions

### What Are Discussions?

Discussions are a separate space in a repository for community conversation. Unlike Issues (which track tasks, bugs, and features), Discussions are for:

- **Questions:** "How do I configure X?"
- **Ideas:** "What if we added support for Y?"
- **Announcements:** "Version 2.0 is released!"
- **General chat:** "Introduce yourself to the community"

### Issues vs Discussions

| Use Issues For... | Use Discussions For... |
|-------------------|------------------------|
| Bug reports | Questions |
| Feature requests | Ideas and brainstorming |
| Specific tasks | Open-ended conversation |
| Things that need tracking | Community building |
| Things that close when done | Ongoing topics |

### Navigating Discussions

1. Go to a repository's main page
2. Press `G` then `G` (double-tap G) to open the navigation menu
3. Select **"Discussions"** from the tabs

Or navigate directly to: `github.com/owner/repo/discussions`

**Screen reader navigation:**
- Press `D` to cycle landmarks to "Main"
- Press `2` or `H` to navigate by headings — each discussion is a heading
- Press `Enter` on a discussion title to open it
- Use `C` to jump to the comment box (if replying)

### Discussion Categories

Repositories can create custom categories:

- **Q&A:** Ask and answer questions (can mark an answer as "accepted")
- **Ideas:** Propose new features or changes
- **Show and Tell:** Share what you built with the project
- **Announcements:** Maintainer updates (often read-only)
- **General:** Everything else

**Q&A format:** Works like StackOverflow — the original poster or a maintainer can mark a reply as the "Answer," which pins it to the top.

### Creating a Discussion

1. Navigate to the Discussions tab
2. Select **"New discussion"**
3. Choose a **category**
4. Add a **title** and **body** (Markdown supported)
5. Select **"Start discussion"**

### Discussion Best Practices

- **Search first** — your question may already be answered
- **Choose the right category** — helps others find your discussion later
- **Be specific** — vague questions get vague answers
- **Mark answers** — if someone solves your problem, mark their reply as the answer (in Q&A discussions)
- **Upvote discussions** — helps maintainers see what the community cares about

### Accessibility Notes

- Discussions use the same accessible interface as Issues
- Screen readers navigate by headings, landmarks, form fields
- Comment editor supports Markdown and has toolbar buttons with labels
- Notification settings for Discussions are separate from Issues—configure in Settings → Notifications

---

## GitHub Wikis

### What Is a GitHub Wiki?

Every repository can have a wiki — a space for documentation separate from the code. It's lightweight and Markdown-based.

**When to use a wiki:**
- Multi-page documentation (tutorials, guides, FAQs)
- Community-editable docs (wikis can be editable by anyone)
- Knowledge that doesn't belong in README (too long, too specific)

**When NOT to use a wiki:**
- Your project already uses GitHub Pages or external docs
- Documentation needs to be version-controlled with code (wikis are separate Git repos)
- You want full control (wikis are less customizable than Pages)

### Accessing a Repo's Wiki

1. Navigate to the repository
2. Select the **"Wiki"** tab
3. If no wiki exists, you'll see "Create the first page"

### Creating Wiki Pages

1. Go to the Wiki tab
2. Select **"New page"**
3. Add a **title** and **content** (Markdown)
4. Select **"Save"**

Wiki pages automatically appear in a sidebar for navigation.

### Wiki Accessibility

- GitHub's wiki editor is the same as the issue/PR comment editor
- All Markdown features work (headings, lists, links, code blocks)
- Use proper heading hierarchy (`##`, `###`) for screen reader navigation
- Link between wiki pages: `[[Page Title]]`
- **Screen reader caveat:** Wiki pages are a separate Git repository. Any changes pushed directly to the wiki's git remote are not tracked by the main repository's branch protection — meaning no PR review process applies. Treat wikis as community-editable supplementary docs, not your primary critical documentation source.

---

## Repository Templates

### Template vs. Fork — Which One?

These are two very different actions that both appear near the "Code" button:

| Action | Use when... | What you get |
|--------|-------------|-------------|
| **Fork** | Contributing back to the original project | Full git history; your changes can be PRed upstream |
| **Use this template** | Starting a *new* project based on the structure | Clean git history; no connection to the original repo |

GitHub Skills courses use **"Use this template"** — you start fresh with the course scaffold but your copy has no upstream connection.

Agent-forge could serve as a template if you want to build your own agent suite starting from its structure without forking.

### Creating a Template Repository

Maintainers can mark any repository as a template:
1. Navigate to the repository's **Settings** tab
2. Scroll to the **"General"** section → find the **"Template repository"** checkbox
3. Check it and save
4. The repository now shows a **"Use this template"** button instead of (or alongside) "Fork"

### Using a Template Repository

1. Navigate to the template repository
2. Select **"Use this template"** button (near the top, next to "Code")
3. Select **"Create a new repository"**
4. Name your new repository, choose visibility, and confirm
5. GitHub creates a new repository with the template's files but **no commit history**

**Screen reader path:**
```
B → navigate buttons → find "Use this template" → Enter
↓ → "Create a new repository" from the dropdown → Enter
```

---

## GitHub Organizations — A Contributor's View

### What Is an Organization?

A GitHub organization is an account that multiple people share. Instead of `github.com/username/repo`, organization repos live at `github.com/org-name/repo`. The workshop's central project lives at `github.com/accesswatch/agent-forge` — `accesswatch` is an organization.

| Personal Account | Organization Account |
|-----------------|---------------------|
| Owned by one person | Shared by a team or community |
| Single-person repos | Repos are shared assets |
| Your profile at `github.com/username` | Org profile at `github.com/org-name` |
| You are the only admin | Has owners, members, and optional teams |

### Joining an Organization

Maintainers can invite you to join. When invited:
1. You receive an email + GitHub notification
2. Navigate to [github.com/settings/organizations](https://github.com/settings/organizations) to accept
3. Or click the link in the invitation email

You can also be a **public contributor** to an org repo without being a member — you fork the repo and submit PRs without needing an invitation.

### Organization Membership Visibility

- By default, your org membership is **private** (only you and org owners can see it)
- You can set it to **public** in your organization membership settings
- Public membership appears on your GitHub profile under "Organizations"
- For `accesswatch`: if you become a member, set your membership public to show your contribution publicly on your profile

### Teams Inside Organizations

Organizations can create **teams** (e.g., `@accesswatch/accessibility-reviewers`). When you see a team mentioned in a PR or issue, that `@mention` notifies everyone on that team. As a contributor, you don't need to create teams — just understand why you see them.

### Navigating an Organization Profile Page

At `github.com/accesswatch`:
```
H → headings: org name, People, Repositories, Projects sections
1 → jumps to the org name heading
Links → navigate to individual repositories, members, and projects
```

Organization-level Projects (like the `accesswatch` project board) appear in the org's Projects tab, not inside any single repository.

---

## Repository Settings — What Contributors Need to Know

You may not have Settings access to most repositories (that requires maintainer role). But knowing what's there helps you understand why a repository behaves the way it does.

### Repository Visibility

| Setting | What it means for contributors |
|---------|-------------------------------|
| **Public** | Anyone can view and fork; you don't need an account to read it |
| **Private** | Only invited users can see or contribute |
| **Internal** (org only) | Visible to all org members; cannot be forked outside the org |

The repository's visibility label appears on its page. Screen readers: the visibility badge is usually near the repo name heading (`H1`).

### Archived Repositories

When a maintainer archives a repository, it becomes **read-only**:
- No new issues, PRs, or comments can be created
- Existing content is fully preserved and viewable
- The UI shows a yellow banner: "This repository has been archived by the owner."
- Screen readers: NVDA/JAWS will read this banner when you navigate to the top of the page with `Ctrl+Home`

If you find a repo you planned to contribute to is archived, look for a fork or successor project.

### Repository Topics

Topics are keyword tags on a repository (e.g., `accessibility`, `screen-reader`, `open-source`). They appear as colored chips on the repository home page and improve discoverability in GitHub search.

- **As a contributor:** Topics tell you what the project is about at a glance
- **As a maintainer:** Add topics in Settings → General → Topics section to improve search ranking
- **Screen reader:** Topics are links in the "About" sidebar section; use `B` (next button) or Links list to reach them

### Default Branch Name

The default branch is the one all PRs target by default. Modern projects use `main`; older projects may use `master` or another name. When you clone and create a branch, you always branch from the repository's default branch.

The default branch name appears in the branch selector at the top of the Code tab.

---

*Return to: [Resources](appendix-q-resources.md) | [Glossary](appendix-a-glossary.md)*
