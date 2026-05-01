# GitHub Learning Resources

---

## Free interactive courses

**GitHub Skills**
https://skills.github.com
GitHub's official learning platform. Browser-based — no setup required. Complete exercises directly in GitHub. Courses cover: Introduction to GitHub, Git branches, PRs, GitHub Actions, GitHub Pages.
Start here if you've never used Git before.

**Pro Git (free book)**
https://git-scm.com/book/en/v2
The definitive Git reference. Free online. You don't need to read it cover-to-cover — use it as a reference when you're confused about a specific concept.

**GitHub Docs**
https://docs.github.com
The official documentation. Well-organized, searchable. Good for looking up specific features.

---

## YouTube

**Traversy Media — Git & GitHub Crash Course For Beginners**
https://www.youtube.com/watch?v=SWYqp7iY_Tc
Classic beginner-friendly walkthrough. 30 minutes. Covers everything you need for day-to-day use.

**Fireship — Git Explained in 100 Seconds**
https://www.youtube.com/watch?v=hwP7WQkmECE
100 seconds of pure clarity. Watch this first.

**Fireship — GitHub Copilot just got way better**
https://www.youtube.com/watch?v=q1G9n2FrZSY
Good overview of AI tools inside GitHub and VS Code.

---

## GitHub CLI

The `gh` command-line tool lets you manage GitHub from your terminal — useful when Claude Code is running commands on your behalf.

Install: https://cli.github.com

Common commands:
```bash
# Authenticate
gh auth login

# Create a repo from current directory
gh repo create

# Open a PR
gh pr create

# List open PRs
gh pr list

# View an issue
gh issue view 42
```

Claude Code uses `gh` internally for PR operations. Having it installed means Claude can create and manage PRs without opening the browser.

---

## GitHub Copilot overview

GitHub Copilot (https://github.com/features/copilot) is Microsoft/GitHub's AI coding assistant:

- **Copilot for autocomplete:** Suggests code as you type in VS Code
- **Copilot Chat:** Chat sidebar in VS Code — ask questions, get explanations
- **Copilot in PRs:** Summarizes what a PR does and suggests reviewers

Pricing: Free tier for students and open source maintainers; $10/month individual; $19/month Business (with org admin controls).

**When to use Copilot vs. Claude Code:**
- Copilot is better for: inline autocomplete while typing, quick code suggestions, GitHub-integrated PR summaries
- Claude Code is better for: multi-step tasks, understanding an entire codebase, writing CLAUDE.md, creating agents, large refactors

Many people run both.
