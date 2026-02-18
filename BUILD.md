# HTML Documentation Build System

This repository automatically converts all markdown files to HTML format.

## Quick Start

### View HTML Documentation

After the first build, all HTML files are available in the `html/` directory:
- Browse them directly in the repo
- Open `html/index.html` in your browser for the homepage
- All markdown files maintain their directory structure

### Local Development

```bash
# Install dependencies (first time only)
npm install

# Build HTML once
npm run build:html

# Watch mode — auto-rebuild on markdown changes
npm run watch:html

# Clean generated files
npm run clean
```

## How It Works

### Automatic Conversion (GitHub Actions)

When you push changes to markdown files on the main branch:
1. GitHub Actions workflow triggers automatically
2. Builds HTML from all `.md` files
3. Commits generated HTML back to the `html/` directory
4. Commit message: "Auto-generate HTML documentation from markdown [skip ci]"

### What Gets Converted

- `docs/*.md` → `html/docs/*.html`
- `learning-room/**/*.md` → `html/learning-room/**/*.html`
- `README.md` → `html/index.html`
- `CONTRIBUTING.md` → `html/CONTRIBUTING.html`
- All other root-level `.md` files

### HTML Features

**Style and Layout:**
- GitHub-flavored Markdown styling (familiar appearance)
- Responsive design (mobile and desktop)
- Syntax highlighting for code blocks
- Clean, readable typography

**Accessibility:**
- Semantic HTML5 markup
- Proper ARIA labels and roles
- Keyboard navigation support
- High contrast mode support
- Skip-to-content links
- Screen reader friendly navigation

**Navigation:**
- Breadcrumb links on every page
- Footer with return link
- Preserves all internal links between documents

## Configuration Files

- **Workflow:** `.github/workflows/build-html.yml` — GitHub Actions automation
- **Build script:** `scripts/build-html.js` — Conversion logic
- **Dependencies:** `package.json` — Node.js packages (marked, highlight.js, etc.)

## Customization

### Modify Styling

Edit `scripts/build-html.js` and look for the `customCss` constant to add custom styles.

### Change HTML Template

Edit the `htmlTemplate` function in `scripts/build-html.js` to modify the page structure.

### Update Dependencies

```bash
# Check for updates
npm outdated

# Update packages
npm update

# Commit package.json changes
git add package.json
git commit -m "chore: update HTML build dependencies"
```

## Troubleshooting

### Build Fails on GitHub Actions

1. Check the **Actions** tab in the repository
2. Click on the failed workflow run
3. Review the error logs
4. Common issues:
   - Markdown syntax errors (unclosed brackets, invalid links)
   - Missing dependencies in `package.json`
   - Permissions issues (workflow needs write access)

### Local Build Errors

**"Cannot find module 'marked'"**
→ Run `npm install` first

**"Permission denied" errors**
→ Check write permissions on the `html/` directory

**HTML doesn't look right**
→ Clear browser cache and reload

**Watch mode not detecting changes**
→ Ensure you're saving files (Ctrl+S in VS Code)

### HTML Files Not Being Committed

Check `.gitignore` to ensure `html/` is NOT listed there. The `html/` directory should be tracked by git.

## For Contributors

When submitting pull requests:
- **Only edit markdown files** — don't commit HTML changes
- HTML will be auto-generated when PR is merged
- To preview HTML locally, run `npm run build:html`
- Add the HTML files to `.gitignore` in your local clone if you don't want to accidentally commit them

## CI/CD Strategy

The `[skip ci]` tag in the auto-commit message prevents infinite loops:
1. You push markdown changes
2. GitHub Actions builds HTML and commits it with `[skip ci]`
3. The commit with `[skip ci]` doesn't trigger another workflow run
4. Clean, single automated commit per markdown update

## Additional Resources

- [marked documentation](https://marked.js.org/) — Markdown parser
- [highlight.js documentation](https://highlightjs.org/) — Syntax highlighting
- [GitHub Actions docs](https://docs.github.com/en/actions) — CI/CD automation
- [GitHub Markdown spec](https://github.github.com/gfm/) — GitHub Flavored Markdown

---

For complete contributor guidelines, see [CONTRIBUTING.md](CONTRIBUTING.md#7-html-documentation-build-system).
