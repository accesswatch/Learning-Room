# Troubleshooting Guide
## Common Issues & Solutions

---

## Table of Contents
- [Setup & Environment](#setup--environment)
- [Git & GitHub](#git--github)
- [VS Code & Copilot](#vs-code--copilot)
- [Templates & YAML](#templates--yaml)
- [Screen Readers & Accessibility](#screen-readers--accessibility)
- [Exercises & Agents](#exercises--agents)

---

## Setup & Environment

### Problem: Git is not installed
**Symptoms:** Terminal shows `git: command not found` or similar error.

**Solution:**
1. **Windows:** Download and install Git for Windows from https://git-scm.com/download/win
2. **macOS:** Run `brew install git` (if Homebrew installed) or download from https://git-scm.com/download/mac
3. **Linux:** Run `sudo apt install git` (Ubuntu/Debian) or equivalent for your distribution
4. Verify: Open terminal and type `git --version`

**Prevention:** Complete the Pre-Workshop Setup (docs/00-pre-workshop-setup.md) before starting.

---

### Problem: GitHub CLI (`gh` command) not found
**Symptoms:** When trying `gh issue list`, terminal shows command not found.

**Solution:**
1. Install GitHub CLI from https://cli.github.com/
2. Authenticate: Run `gh auth login` and follow prompts
3. Verify: Type `gh --version`

**Note:** GitHub CLI is optional but recommended for faster issue/PR workflows.

---

### Problem: No GitHub account or fork of the repository
**Symptoms:** Can't clone, can't push, can't make pull requests.

**Solution:**
1. Create GitHub account at https://github.com (free tier is fine)
2. Navigate to the original repository
3. Click **Fork** button (top-right) → Creates your copy
4. Clone YOUR fork: `git clone https://github.com/YOUR-USERNAME/REPO-NAME.git`
5. Verify fork worked: `git remote -v` (should show your fork's URL)

---

## Git & GitHub

### Problem: Authentication fails when pushing
**Symptoms:** "Permission denied" or "Could not read from repository" when running `git push`.

**Causes & Solutions:**

**Option A: SSH Key not set up**
1. Generate key: `ssh-keygen -t ed25519 -C "your_email@example.com"`
2. Accept defaults (press Enter 3 times)
3. Add to GitHub: https://github.com/settings/ssh/new
4. Copy key: 
   - **Windows/Linux:** `cat ~/.ssh/id_ed25519.pub` (then copy output)
   - **macOS:** `cat ~/.ssh/id_ed25519.pub | pbcopy` (auto-copies)
5. Paste into GitHub SSH key field
6. Test: `ssh -T git@github.com` (should say "Hi [USERNAME]!")

**Option B: Using HTTPS instead of SSH**
1. On GitHub, generate Personal Access Token: https://github.com/settings/tokens
2. Use token as password when prompted after `git push`
3. Or use credential storage: `git config --global credential.helper store` (saves token securely)

**Option C: Wrong remote URL**
1. Check: `git remote -v`
2. Should show `origin https://github.com/YOUR-USER/REPO.git`
3. Fix if needed: `git remote set-url origin https://github.com/YOUR-USER/REPO.git`

---

### Problem: "Fatal: not a git repository"
**Symptoms:** Running git commands gives this error.

**Solution:**
1. Verify you're in the correct folder: `pwd` (or `Get-Location` on Windows)
2. Check for `.git` folder: `ls -la` (or `Get-ChildItem -Force` on Windows)
3. If not a git repo, you cloned incorrectly. Delete and re-clone:
   ```bash
   cd ..                                    # Go up one level
   rm -rf REPO-NAME                         # Delete folder
   git clone https://github.com/YOUR-USER/REPO.git
   cd REPO-NAME
   ```

---

### Problem: Large merge conflict (don't know how to resolve)
**Symptoms:** File shows `<<<<<<< HEAD ... ======= ... >>>>>>> branch-name` markers.

**Solution - Simple Approach:**
1. **Keep YOUR changes:** `git checkout --ours [filename]`
2. **Keep THEIR changes:** `git checkout --theirs [filename]`
3. **Abort everything:** `git merge --abort` (restarts)

**Solution - Manual Merge (Advanced):**
1. Open file in VS Code
2. Look for conflict markers (<<<< ==== >>>>)
3. Delete the version you don't want
4. Remove all conflict markers
5. Run: `git add [filename]` → `git commit -m "Resolved merge conflict"`

**Prevention:** Pull upstream regularly (`git pull upstream main`) to avoid stale branches.

---

## VS Code & Copilot

### Problem: Copilot Chat panel won't open
**Symptoms:** Copilot Chat icon is grayed out, or Ctrl+Shift+I does nothing.

**Solution:**
1. Verify GitHub Copilot extension installed:
   - Open Extensions: `Ctrl+Shift+X`
   - Search "GitHub Copilot"
   - Should show installed with green checkmark
2. If not installed, click **Install**
3. If installed but grayed out, reload window:
   - `Ctrl+Shift+P` → type "Reload Window" → press Enter
4. Check GitHub Copilot subscription (requires paid plan or organization access)
5. Verify you're signed in to GitHub: Click GitHub icon (bottom-left) → Sign in if needed

---

### Problem: Chat says "You don't have access to Copilot"
**Symptoms:** Even though you have Copilot installed.

**Solution:**
1. You may need a GitHub Copilot subscription (paid, ~$10/month)
2. Or organization membership with Copilot enabled
3. Check your account at https://github.com/copilot/signup
4. If not active, upgrade or contact organization admin
5. **For students/educators:** Free access https://education.github.com/

---

### Problem: VS Code extensions not loading
**Symptoms:** Copilot or other extensions crash or don't appear.

**Solution:**
1. Open command palette: `Ctrl+Shift+P`
2. Type "Developer: Reload Window" → press Enter
3. If still broken, check extensions folder for conflicts:
   - Close VS Code
   - Delete `.vscode/extensions` folder (be careful!)
   - Reopen VS Code (extensions will reinstall)
4. Check for extension errors: View → Output → Select "Copilot" from dropdown

---

### Problem: File saved but git status still shows as modified
**Symptoms:** You saved your work but `git status` says file is changed.

**Solution:**
1. Verify file is actually saved: Look for white dot on tab (indicates unsaved)
2. Manually save: `Ctrl+S`
3. Check line endings (Windows vs. Unix):
   - Bottom-right corner shows "LF" or "CRLF"
   - GitHub expects "LF" for most files
   - Click and change if necessary
4. Try: `git add [filename]` → see if it stages properly

---

## Templates & YAML

### Problem: "Template not showing in GitHub issue creation"
**Symptoms:** Click "New Issue" but your custom template doesn't appear, or shows as "Blank" only.

**Causes & Solutions:**

**Issue A: File in wrong location**
- Should be: `.github/ISSUE_TEMPLATE/your-template.yml`
- Not: `.github/ISSUE_TEMPLATE/your-template.md` (wrong extension)
- Not: `.github/your-template.yml` (wrong folder)

**Issue B: YAML syntax errors**
- Check for:
  - Missing colons after field names: `name:` not `name`
  - Inconsistent indentation (use spaces, not tabs)
  - Mismatched quotes: `"` or `'` must close properly
- Validate at: https://www.yamllint.com/ (paste YAML, should show ✓)

**Issue C: Not committed to main branch**
- These files must be on GitHub's `main` or `master` branch
- Check: `git branch` (should be on main) then `git push origin main`
- Verify on GitHub web: browse to `.github/ISSUE_TEMPLATE/` folder

**Issue D: Browser cache**
- Try: Hard refresh (Ctrl+Shift+R or Cmd+Shift+R)
- Or: Windows → Private browsing / Incognito → try again

---

### Problem: "Required field" validation not working
**Symptoms:** You marked a field as `required: true` but it lets users submit without filling it.

**Solution:**
1. Verify correct YAML nesting:
   ```yaml
   - type: input
     id: version
     attributes:
       label: Version
     validations:              # Part of TYPE, not attributes
       required: true          # Correct level
   ```
2. Not like this (too nested):
   ```yaml
   - type: input
     attributes:
       label: Version
       validations:            # WRONG: Inside attributes
         required: true
   ```
3. Commit changes: `git push origin main`
4. Clear cache on GitHub (Ctrl+Shift+R)

---

### Problem: Markdown inside template not rendering
**Symptoms:** Markdown text appears as raw asterisks/hashes instead of formatted.

**Solution:**
1. Verify correct field type:
   - Markdown/instructions: Use `type: markdown`
   - Form field labels: Use `type: input` or `type: textarea`
2. For markdown fields, correct structure:
   ```yaml
   - type: markdown
     attributes:
       value: |
         ## Your heading here
         **Bold text** and *italic*
   ```
3. The `|` after `value:` is required (tells YAML it's multi-line)

---

## Screen Readers & Accessibility

### Problem: NVDA not reading GitHub page
**Symptoms:** Screen reader launches but nothing happens or misses content.

**Solution - NVDA:**
1. Verify browse mode vs. focus mode:
   - Launch NVDA → press `NVDA+Space` to toggle
   - For web, use browse mode (default)
2. Use navigation keys:
   - `H` for headings
   - `D` for landmarks (navigation, main content)
   - `B` for buttons, `L` for lists
3. Report issues: If specific page not accessible, note URL and file issue with WCAG compliance feedback

---

### Problem: JAWS not announcing form fields correctly
**Symptoms:** JAWS skips form inputs or doesn't say "required".

**Solution - JAWS:**
1. Enable "Forms Mode" automatically: `Insert+Z` (toggle)
2. Use `Insert+F6` to list all form controls on page
3. Check field labels: If not announced, check GitHub template YAML has `label:` attribute
4. Report: If needed, create accessibility issue with JAWS version and page URL

---

### Problem: VoiceOver on macOS not reading GitHub elements
**Symptoms:** VoiceOver skips buttons, links, or form fields.

**Solution - VoiceOver:**
1. Open rotor: `VO+U` (Mac Voice Over key is usually Caps Lock or Control+Option)
2. Navigate by category (Headings, Links, Form Controls)
3. If rotor doesn't show content, may be a GitHub rendering issue
4. Test in Safari (often more compatible with VoiceOver)
5. Report: Screenshot or recording with page URL to accessibility team

---

### Problem: "Form fields not marked as required for screen readers"
**Symptoms:** Screen reader doesn't announce which fields are required.

**Solution:**
1. In template YAML, use this structure:
   ```yaml
   - type: input
     id: field_id
     attributes:
       label: Field Label
     validations:
       required: true
   ```
2. GitHub automatically announces `required` if set correctly
3. Test by:
   - Opening template issue form
   - Pressing `Tab` to move to field
   - Screen reader should say: "[label] required" or "[label] edit text, required"

---

## Exercises & Agents

### Problem: "Can't find the @template-builder agent"
**Symptoms:** In VS Code Copilot Chat, `@template-builder` doesn't appear or autocomplete.

**Solution:**
1. Verify you have GitHub Copilot (not just free tier)
2. Ensure `.github/agents/template-builder.agent.md` exists in repository
3. Reload VS Code: `Ctrl+Shift+P` → "Reload Window"
4. Open Copilot Chat: `Ctrl+Shift+I`
5. Type `@` and scroll to see available agents
6. If still missing:
   - Check file is on `main` branch: `git log --oneline .github/agents/template-builder.agent.md`
   - Force push if needed: `git push origin main`
   - Wait 2-3 minutes for agent index to refresh

---

### Problem: Agent gives generic advice instead of using the agent's persona
**Symptoms:** You ask @template-builder something but it responds like @issue-tracker.

**Solution:**
1. Reload Copilot: Close chat panel and reopen (`Ctrl+Shift+I`)
2. Verify you @ mentioned agent correctly: `@template-builder` (exact name)
3. Use agent-specific slash commands: Type `/` in chat to see available commands
4. If agent still generic:
   - Check `.agent.md` file syntax (must be valid YAML frontmatter)
   - Verify system prompt describes the agent's role clearly
   - Test with simpler question first

---

### Problem: "Exercise tells me to look for a file but I can't find it"
**Symptoms:** Exercise says "open the template file" but you don't see it.

**Solution:**
1. Verify repository structure:
   ```bash
   ls -R .github/               # Show all .github files
   ```
2. Check exercise prerequisite: Is the file supposed to already exist?
3. For templates: Should be in `.github/ISSUE_TEMPLATE/` folder
4. For agents: Should be in `.github/agents/` folder
5. Not there? You may have skipped a step:
   - Exercise A (create template) must be done before Exercise B (clone & edit)
   - Ask facilitator or re-read prerequisites

---

### Problem: Exercise tests pass locally but fail on GitHub
**Symptoms:** Works when you test file locally, but GitHub Actions or PR validation fails.

**Solution:**
1. Check YAML file exactly matches requirements:
   - Case-sensitive filenames: `accessibility-bug.yml` not `accessibility-BUG.yml`
   - Line endings: GitHub expects Unix (LF), not Windows (CRLF)
   - Fix in VS Code: Bottom-right, click "CRLF" → change to "LF"
2. Verify GitHub sees the new file:
   - Push: `git add . → git commit -m "..." → git push origin [branch]`
   - Check on GitHub.com (refresh browser)
3. Check Actions/Validation output:
   - On your PR, scroll to "Checks" section
   - Click failing check → see error message → fix file and push again

---

### Problem: "Can't understand what the exercise is asking me to do"
**Symptoms:** Exercise steps are confusing or contradict each other.

**Solution:**
1. Read prerequisites first: Each exercise lists what's required
2. Look for examples: Most exercises link to reference files or screenshots
3. Follow the "What you should see" checkpoint:
   - After each step, there's a description of what success looks like
   - If your screen doesn't match, re-read the step
4. Try the backup steps: Most exercises have "If you're stuck..." section
5. Ask for help:
   - Post in discussion forum or issue tracker
   - Provide screenshot of what you're seeing
   - Include exercise number and step number

---

### Problem: Copilot Chat freezes or stops responding
**Symptoms:** Chat input becomes unresponsive, may show loading indefinitely.

**Solution:**
1. Wait 10-15 seconds (Chat API may be slow)
2. Reload Copilot:
   - Close chat panel (X button)
   - Open again: `Ctrl+Shift+I`
3. Check internet connection (Copilot requires active network)
4. If terminal shows error, check output:
   - View → Output → Select "GitHub Copilot" from dropdown
   - Look for error messages
5. Restart VS Code if needed:
   - Save work first
   - Close completely
   - Reopen

---

## Getting Help

If you can't find your issue here:

1. **Check the Glossary:** `docs/appendix-a-glossary.md` (term definitions)
2. **Accessibility Cheatsheet:** `docs/appendix-b-screen-reader-cheatsheet.md` (screen reader commands)
3. **Resources:** `RESOURCES.md` (links, documentation, support)
4. **Issues:** Open an issue on GitHub with:
   - What you tried
   - What happened
   - What you expected
   - Screenshot if possible
   - Screen reader used (if accessibility issue)

---

*Last updated: February 2026 | Maintained by GitHub Learning Community*
