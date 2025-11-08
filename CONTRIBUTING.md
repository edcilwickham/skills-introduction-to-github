# Contributing to Introduction to GitHub

Thank you for your interest in contributing to this project! This document provides guidelines and instructions for contributing.

## Getting Started with GitHub

### Prerequisites

Before you can contribute, you'll need:

1. **A GitHub Account**: Sign up at [github.com](https://github.com)
2. **Git Installed**: Download from [git-scm.com](https://git-scm.com)
3. **Basic Git Knowledge**: Familiarize yourself with Git basics

### Setting Up Git

Configure your Git username and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Connecting to GitHub

#### Using HTTPS

1. Clone the repository:
   ```bash
   git clone https://github.com/edcilwickham/skills-introduction-to-github.git
   ```

2. Navigate to the repository:
   ```bash
   cd skills-introduction-to-github
   ```

#### Using SSH (Recommended)

1. Generate an SSH key (if you don't have one):
   ```bash
   ssh-keygen -t ed25519 -C "your.email@example.com"
   ```

2. Add the SSH key to your GitHub account:
   - Copy your public key: `cat ~/.ssh/id_ed25519.pub`
   - Go to GitHub Settings → SSH and GPG keys → New SSH key
   - Paste your key and save

3. Clone the repository using SSH:
   ```bash
   git clone git@github.com:edcilwickham/skills-introduction-to-github.git
   ```

## How to Contribute

### 1. Fork the Repository

Click the "Fork" button at the top right of the repository page.

### 2. Clone Your Fork

```bash
git clone https://github.com/YOUR_USERNAME/skills-introduction-to-github.git
cd skills-introduction-to-github
```

### 3. Create a Branch

```bash
git checkout -b feature/your-feature-name
```

Branch naming conventions:
- `feature/` - for new features
- `fix/` - for bug fixes
- `docs/` - for documentation updates
- `refactor/` - for code refactoring

### 4. Make Your Changes

- Write clear, concise commit messages
- Follow the existing code style
- Test your changes thoroughly
- Update documentation as needed

### 5. Commit Your Changes

```bash
git add .
git commit -m "Add a clear description of your changes"
```

### 6. Push to Your Fork

```bash
git push origin feature/your-feature-name
```

### 7. Open a Pull Request

1. Go to the original repository on GitHub
2. Click "Pull requests" → "New pull request"
3. Click "compare across forks"
4. Select your fork and branch
5. Fill out the PR template with:
   - Clear description of changes
   - Related issue number (if applicable)
   - Screenshots (if applicable)

## Pull Request Guidelines

- **One feature per PR**: Keep PRs focused on a single feature or fix
- **Update documentation**: Include relevant documentation updates
- **Write tests**: Add tests for new features when applicable
- **Follow code style**: Match the existing code style
- **Descriptive titles**: Use clear, descriptive PR titles

## Code Review Process

1. A maintainer will review your PR
2. Address any requested changes
3. Once approved, your PR will be merged
4. Your contribution will be credited in the repository

## Reporting Issues

Found a bug or have a suggestion? Please:

1. Check if the issue already exists
2. If not, create a new issue with:
   - Clear, descriptive title
   - Detailed description
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior
   - Screenshots if applicable

## GitHub Features to Use

### Issues

- Use for bug reports, feature requests, and discussions
- Add labels to categorize issues
- Reference issues in commits with `#issue-number`

### Pull Requests

- Use for proposing changes
- Request reviews from maintainers
- Link related issues

### Discussions

- Use for general questions and ideas
- Share tips and best practices
- Get help from the community

### Projects

- Track progress on features
- Organize issues and PRs
- Plan releases

## Additional Resources

- [GitHub Docs](https://docs.github.com)
- [GitHub Skills](https://skills.github.com)
- [Git Documentation](https://git-scm.com/doc)
- [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)

## Questions?

If you have questions about contributing, feel free to:
- Open an issue
- Start a discussion
- Contact the maintainers

Thank you for contributing! 🎉
