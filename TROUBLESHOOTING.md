# GitHub Connection Troubleshooting Guide

This guide helps you troubleshoot common GitHub connection and functionality issues.

## Table of Contents

- [Authentication Issues](#authentication-issues)
- [Connection Problems](#connection-problems)
- [Git Configuration](#git-configuration)
- [GitHub Actions Issues](#github-actions-issues)
- [Common Errors](#common-errors)

## Authentication Issues

### SSH Authentication

If you're having trouble connecting via SSH:

1. **Check if SSH key exists:**
   ```bash
   ls -la ~/.ssh
   ```
   Look for `id_ed25519.pub` or `id_rsa.pub`

2. **Generate a new SSH key:**
   ```bash
   ssh-keygen -t ed25519 -C "your.email@example.com"
   ```

3. **Add SSH key to ssh-agent:**
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

4. **Copy public key:**
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

5. **Add to GitHub:**
   - Go to GitHub Settings → SSH and GPG keys
   - Click "New SSH key"
   - Paste your key and save

6. **Test connection:**
   ```bash
   ssh -T git@github.com
   ```
   You should see: "Hi username! You've successfully authenticated..."

### HTTPS Authentication

If using HTTPS and getting authentication errors:

1. **Use Personal Access Token (PAT):**
   - Go to GitHub Settings → Developer settings → Personal access tokens
   - Generate new token with appropriate scopes
   - Use the token as your password when prompted

2. **Cache credentials:**
   ```bash
   git config --global credential.helper cache
   ```

3. **Store credentials (use with caution):**
   ```bash
   git config --global credential.helper store
   ```

## Connection Problems

### Cannot Push/Pull

1. **Check remote URL:**
   ```bash
   git remote -v
   ```

2. **Update remote URL if needed:**
   ```bash
   # For HTTPS
   git remote set-url origin https://github.com/username/repo.git
   
   # For SSH
   git remote set-url origin git@github.com:username/repo.git
   ```

3. **Verify network connectivity:**
   ```bash
   ping github.com
   ```

4. **Check if behind a proxy:**
   ```bash
   git config --global http.proxy http://proxy.example.com:8080
   git config --global https.proxy https://proxy.example.com:8080
   ```

### Rate Limiting

If you encounter rate limiting:

1. **Authenticate your requests** to increase limits
2. **Use a Personal Access Token** for API calls
3. **Wait for the rate limit to reset** (check headers for reset time)

## Git Configuration

### Set User Information

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Verify Configuration

```bash
git config --list
```

### Set Default Branch Name

```bash
git config --global init.defaultBranch main
```

### Configure Line Endings

**Windows:**
```bash
git config --global core.autocrlf true
```

**Mac/Linux:**
```bash
git config --global core.autocrlf input
```

## GitHub Actions Issues

### Workflows Not Running

1. **Check if Actions are enabled:**
   - Go to repository Settings → Actions → General
   - Ensure Actions are enabled

2. **Verify workflow file syntax:**
   - Check YAML syntax in `.github/workflows/` files
   - Use a YAML validator

3. **Check workflow triggers:**
   - Verify events in the `on:` section
   - Ensure conditions are met

4. **Review permissions:**
   - Check if workflow has necessary permissions
   - Verify `GITHUB_TOKEN` scopes

### Workflow Failures

1. **Check workflow logs:**
   - Go to Actions tab
   - Click on the failed workflow
   - Review error messages

2. **Common issues:**
   - Missing secrets or environment variables
   - Incorrect file paths
   - Permission errors
   - Timeout issues

## Common Errors

### "Permission denied (publickey)"

**Solution:**
- Check SSH key is added to GitHub
- Verify ssh-agent is running
- Use `ssh -Tv git@github.com` for verbose output

### "fatal: remote origin already exists"

**Solution:**
```bash
git remote rm origin
git remote add origin <repository-url>
```

### "fatal: refusing to merge unrelated histories"

**Solution:**
```bash
git pull origin main --allow-unrelated-histories
```

### "Updates were rejected because the tip of your current branch is behind"

**Solution:**
```bash
git pull origin main --rebase
```

### "fatal: not a git repository"

**Solution:**
```bash
git init
```

## Repository-Specific Issues

### This Repository

This repository uses GitHub Actions for automated workflows. If you're experiencing issues:

1. **Verify you're on the correct branch:**
   ```bash
   git branch
   ```

2. **Check step tracker:**
   ```bash
   cat .github/steps/-step.txt
   ```

3. **Ensure workflows can run:**
   - Repository must not be a template
   - Actions must be enabled
   - Required permissions must be set

## Getting Help

If you're still experiencing issues:

1. **Check GitHub Status:** [githubstatus.com](https://www.githubstatus.com)
2. **Review GitHub Docs:** [docs.github.com](https://docs.github.com)
3. **Search Community Discussions:** [github.com/community/community](https://github.com/orgs/community/discussions)
4. **Open an Issue:** Create an issue in this repository with:
   - Description of the problem
   - Steps to reproduce
   - Error messages
   - Your environment (OS, Git version)

## Additional Resources

- [GitHub Documentation](https://docs.github.com)
- [GitHub Skills](https://skills.github.com)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Community Forum](https://github.com/orgs/community/discussions)
- [GitHub Support](https://support.github.com)

---

**Need immediate help?** Check our [Discussions](https://github.com/orgs/skills/discussions/categories/introduction-to-github) for this course.
