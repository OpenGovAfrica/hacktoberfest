# Contributing to OpenGov Africa

Welcome to OpenGov Africa! This guide is for beginners who want to contribute to OpenGov Africa repositories.

## Table of Contents

- [Getting Started](#getting-started)
- [Making Your Contribution](#making-your-contribution)
- [Handling Merge Conflicts](#handling-merge-conflicts)
- [Testing Your Changes](#testing-your-changes)
- [Best Practices](#best-practices)
- [Getting Help](#getting-help)


## Getting Started

### 1. Fork the Repository

Click the **Fork** button in the top-right corner of the repository page. This creates your own copy of the project.

### 2. Clone Your Fork

Open your terminal and run:

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

Replace `<your-username>` with your GitHub username and `<repo-name>` with the repository name.

### 3. Set Up the Upstream Remote

This connects your local repository to the original project so you can sync changes:

```bash
git remote add upstream https://github.com/OpenGovAfrica/<repo-name>.git
git fetch upstream
```

### 4. Create a Feature Branch

Always create a new branch for your changes:

```bash
git checkout -b feature/your-feature-name
```

**Branch naming conventions:**

- `feature/` for new features
- `fix/` for bug fixes
- `docs/` for documentation updates
- Example: `docs/update-readme` or `fix/typo-in-homepage`

## Making Your Contribution

### 1. Make Your Changes

Keep your changes focused on a single improvement:

- Fix a bug
- Add documentation
- Improve code readability
- Add tests

### 2. Stage Your Changes

Review what you've changed:

```bash
git status
```

Stage the files you want to commit:

```bash
git add <filename>
# Or stage all changes:
git add .
```

### 3. Commit Your Changes

Write a clear, descriptive commit message:

```bash
git commit -m "type: brief description of changes"
```

**Commit message types:**

- `feat:` new feature
- `fix:` bug fix
- `docs:` documentation changes
- `style:` formatting, missing semicolons, etc.
- `refactor:` code restructuring
- `test:` adding tests
- `chore:` maintenance tasks

**Example:**

```bash
git commit -m "docs: add installation instructions to README"
```

### 4. Push Your Branch

```bash
git push origin feature/your-feature-name
```

### 5. Open a Pull Request

1. Go to your fork on GitHub
2. You'll see a **Compare & pull request** button—click it
3. Fill out the PR template:

**Title:** Use the same format as your commit message

```
docs: add installation instructions to README
```

**Description template:**

```markdown
## What does this PR do?
Briefly describe your changes

## Why is this needed?
Explain the problem this solves or the value it adds

## Type of change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Code refactoring

## Testing
- [ ] I have tested these changes locally
- [ ] I have added tests (if applicable)

## Screenshots (if applicable)
Add before/after screenshots for UI changes
```

4. Click **Create pull request**
5. Wait for a maintainer to review your PR

## Handling Merge Conflicts

Merge conflicts happen when someone else has changed the same files you're working on. Don't panic—they're easy to fix!

### Method 1: Rebase (Recommended)

This keeps your commit history clean:

```bash
# Update your main branch
git checkout main
git pull upstream main

# Rebase your feature branch
git checkout feature/your-feature-name
git rebase upstream/main
```

If conflicts occur:

1. Git will pause and show which files have conflicts
2. Open the conflicted files and look for conflict markers:

```
<<<<<<< HEAD
Current code from main branch
=======
Your changes
>>>>>>> feature/your-feature-name
```

3. Edit the file to keep the correct code and remove the markers
4. Stage the resolved files:

```bash
git add <resolved-file>
```

5. Continue the rebase:

```bash
git rebase --continue
```

6. Force push your changes:

```bash
git push --force-with-lease origin feature/your-feature-name
```

### Method 2: Merge (Simpler Alternative)

```bash
git checkout feature/your-feature-name
git merge upstream/main
```

Resolve conflicts as described above, then:

```bash
git add <resolved-file>
git commit -m "merge: resolve conflicts with main"
git push origin feature/your-feature-name
```

## Testing Your Changes

### For Documentation Changes

Preview your markdown files to ensure formatting is correct. Most documentation PRs don't require additional testing.

### For Code Changes

**Python projects:**

```bash
# Create a virtual environment
python -m venv .venv

# Activate it
# Windows:
.venv\Scripts\activate
# Mac/Linux:
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run tests
pytest

# Run linting
flake8
```

**JavaScript/Node.js projects:**

```bash
# Install dependencies
npm ci

# Run tests
npm test

# Run linting
npm run lint

# Build (if applicable)
npm run build
```

## Best Practices

### Do's ✅

- Keep PRs small and focused on one thing
- Write clear, descriptive commit messages
- Test your changes before submitting
- Ask questions if you're unsure
- Be patient and respectful during code review
- Update your branch if maintainers request changes

### Don'ts ❌

- Don't work directly on the `main` branch
- Don't submit massive PRs with unrelated changes
- Don't force push to `main` (you can't anyway, but good to know!)

## Getting Help

Stuck? We're here to help!

- **Issues:** Check existing [issues](../../issues) or open a new one
- **Discussions:** Join our [community discussions](../../discussions)
- **Discord/Slack:** [Join our community](#) (add your community link)
- **Maintainers:** Tag maintainers in your PR if you need guidance

Remember: Everyone was a beginner once. Don't be afraid to ask questions or make mistakes—that's how we all learn!

---

## Quick Reference

```bash
# Initial setup
git clone https://github.com/<your-username>/<repo>.git
cd <repo>
git remote add upstream https://github.com/OpenGovAfrica/<repo>.git

# For each contribution
git checkout main
git pull upstream main
git checkout -b feature/your-feature
# Make changes
git add .
git commit -m "type: description"
git push origin feature/your-feature
# Open PR on GitHub

# Update your branch
git fetch upstream
git rebase upstream/main
git push --force-with-lease origin feature/your-feature
```

---

**Happy contributing! 🎉**



