# Contributing to Conn

Thank you for your interest in contributing to Conn! We welcome contributions from everyone, especially GSSoC 2026 participants.

## 🚀 Getting Started

### For GSSoC 2026 Participants

1. **Fork the repository** on GitHub
2. **Star the repository** (optional but appreciated!)
3. **Clone your fork** locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/Conn.git
   cd Conn
   ```
4. **Add the original repository as upstream**:
   ```bash
   git remote add upstream https://github.com/mayo-byte07/Conn.git
   ```

## 🛠️ Development Setup

For detailed installation and setup instructions, please refer to the [README.md](README.md#quick-start-local-development) Quick Start section.

**Quick reference:**
- Fork and clone the repository
- Run `npm install`
- Set up your `.env` file with Supabase credentials
- Run `npm start` to begin development

## 📋 Contribution Workflow & Guidelines

### 1. Issue Lifecycle & Selection

- **Search First:** Before opening a new issue, check if it already exists.
- **Find an Issue:** Look for issues labeled `gssoc`, `good first issue`, `bug`, or `enhancement`.
- **Claiming:** Comment "I would like to work on this" on the issue. **Wait for a maintainer to assign it to you** before you begin coding.
- **Limits:** Please claim only one issue at a time to give everyone a fair chance to contribute.
- **Stale Issues:** If an issue is assigned but shows no activity for 7 days, it may be reassigned.

### 2. Branching Strategy

A clean Git tree makes review easier. Always branch off of `main` and use the following naming conventions:
- **Features:** `feature/short-description` (e.g., `feature/dark-mode`)
- **Bug Fixes:** `fix/issue-description` (e.g., `fix/auth-cookie-bug`)
- **Documentation:** `docs/what-was-updated` (e.g., `docs/api-endpoints`)
- **GSSoC Participants:** Prefix your branch with `gssoc/` (e.g., `gssoc/feature/add-social-icons`)

### 3. Commit Standards

We use [Conventional Commits](https://www.conventionalcommits.org/). Your commit messages should be structured as follows:
- `feat: add dark mode toggle` (New feature)
- `fix: resolve login authentication error` (Bug fix)
- `docs: update API documentation` (Documentation only)
- `style: format code with prettier` (Formatting, missing semi-colons, etc)
- `refactor: simplify link management logic` (Code change that neither fixes a bug nor adds a feature)
- `test: add unit tests for auth module` (Adding missing tests)

### 4. Pull Request Process

1. **Sync your fork** with the latest upstream changes to avoid merge conflicts:
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```
2. **Push to your fork**:
   ```bash
   git push origin gssoc/feature/your-feature-name
   ```
3. **Open a Pull Request** against the upstream `main` branch. Ensure your PR includes:
   - A clear, descriptive title (`feat: add custom backgrounds`)
   - A detailed description explaining the "Why" and "What" of your changes.
   - The phrase `Fixes #ISSUE_NUMBER` to auto-close the issue on merge.
   - **Visual Proof:** Screenshots or screen recordings if you modified the UI.
4. **Review:** Maintainers will review your PR. Be open to feedback and ready to make requested changes!

## 🎯 Code Style Guidelines

### JavaScript
- Use camelCase for variables and functions
- Use PascalCase for classes and constructors
- Add JSDoc comments for complex functions
- Keep functions small and focused

### HTML/CSS
- Use semantic HTML elements
- Follow BEM naming convention for CSS classes
- Ensure responsive design (mobile-first approach)
- Test on multiple screen sizes

### General
- Write clean, readable code
- Add comments for complex logic
- Remove console.log statements before submitting
- Ensure no sensitive data is committed

## 🧪 Testing

- Test your changes thoroughly before submitting
- Check for cross-browser compatibility
- Test on mobile devices
- Verify existing features still work

## 📝 Documentation

- Update relevant documentation if your change affects it
- Add comments to complex code sections
- Update API documentation if you modify endpoints
- Add examples for new features

## 🐛 Bug Reports

When reporting bugs, include:
- Clear description of the problem
- Steps to reproduce
- Expected vs actual behavior
- Screenshots if applicable
- Environment details (OS, browser, Node.js version)

## 💡 Feature Requests

When suggesting features:
- Describe the use case
- Explain why it would be valuable
- Consider implementation complexity
- Provide mockups if it's a UI change


## ⭐ GSSoC 2026 Specific Rules

1. **Quality over quantity**: Focus on meaningful contributions
2. **Communication is key**: Keep maintainers updated on your progress
3. **Ask for help**: If you're stuck, reach out via Discussions
4. **Be patient**: Reviewers may take time to respond
5. **Learn and grow**: Use this opportunity to improve your skills

## 📊 Project Areas for Contribution

- **Frontend**: UI improvements, new themes, animations
- **Backend**: API optimizations, new endpoints
- **Database**: Schema improvements, query optimization
- **Features**: Analytics, social integrations, payment flows
- **Documentation**: README, API docs, tutorials
- **Testing**: Unit tests, integration tests
- **Bug Fixes**: Any reported issues

## 🌟 First Contribution Tips

- Read the issue carefully before starting work
- Keep pull requests focused on a single issue
- Test documentation formatting before submitting
- Sync your fork regularly with the upstream repository
- Be respectful and open to review feedback



## 🎉 Recognition

- Contributors will be listed in the CONTRIBUTORS.md file
- Outstanding contributions may be featured in project releases
- GSSoC participants who complete their goals will receive certificates

---

**Happy Contributing!** 🚀

For project contact information, please see the [README.md](README.md#contact) Contact section.
