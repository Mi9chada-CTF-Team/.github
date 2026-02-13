#  Contributing to Mi9chada CTF Team

Thank you for your interest in contributing to **Mi9chada** ! We welcome contributions from UM6P students and the broader security community to help grow our knowledge base, tooling, and training resources.

---

##  Table of Contents

- [Code of Conduct](#-code-of-conduct)
- [How to Contribute](#-how-to-contribute)
  - [Writeups](#writeups)
  - [Training Materials](#training-materials)
  - [Toolkit & Scripts](#toolkit--scripts)
  - [Original Challenges](#original-challenges)
- [Contribution Workflow](#-contribution-workflow)
- [Style Guidelines](#-style-guidelines)
- [Security Policy](#-security-policy)
- [Getting Help](#-getting-help)
- [Recognition](#-recognition)

---

##  Code of Conduct

By participating in this project, you agree to uphold our [Code of Conduct](CODE_OF_CONDUCT.md):
- Be respectful and inclusive
- No harassment or discrimination
- Credit original authors when reusing content
- **Never publish live flags or solutions to ongoing CTFs**
- Respect competition rules and responsible disclosure principles

Violations will result in contribution privileges being revoked.

---

##  How to Contribute

###  Writeups

We accept detailed writeups for competitions where:
-  The competition has **ended** (no ongoing events)
-  Solutions don't violate competition rules (e.g., no NDAs)
-  Content is original or properly attributed

**Required structure** (`writeups/_posts/YYYY-MM-DD-competition-name.md`):
```markdown
---
layout: post
title: "Competition Name"
date: YYYY-MM-DD
categories: [International/National/Regional, Year]
tags: [web, pwn, crypto, rev, forensics, misc]
authors: ["@github-handle1", "@github-handle2"]
competition: "Full Competition Name"
---

# Challenge Name

## Description
Brief challenge context...

## Solution
Step-by-step walkthrough with:
- Vulnerability analysis
- Exploit development (with code blocks)
- Screenshots/diagrams where helpful
- Final flag format (redacted: `FLAG{redacted_example}`)

## Lessons Learned
What did we learn? How to avoid similar pitfalls?
```

⚠️ **Never include**:
- Live flags from ongoing competitions
- Credentials, API keys, or sensitive infrastructure details
- Unredacted flags from competitions with explicit NDAs

---

###  Training Materials

Help us build better learning resources for new members:

| Resource Type | Location | Guidelines |
|---------------|----------|------------|
| Beginner guides | `training/basics/` | Assume zero prior knowledge; include setup instructions |
| Challenge sets | `training/challenges/` | Provide difficulty rating (Easy/Medium/Hard) |
| Tool tutorials | `training/tools/` | Focus on practical usage, not just theory |
| Cheat sheets | `training/cheatsheets/` | Concise, copy-paste friendly commands |

**Template for new challenges**:
```yaml
# training/challenges/web/sql-injection-101/challenge.yml
name: "SQL Injection 101"
category: "web"
difficulty: "easy"
description: "Basic UNION-based SQL injection"
solution_path: "solution.md"
tags: ["sqli", "beginner"]
estimated_time: "15 minutes"
```

---

###  Toolkit & Scripts

We maintain a collection of utilities used during competitions:

**Requirements for script contributions**:
-  Must solve a **real problem** encountered in CTFs
-  Include a `README.md` explaining:
  - Purpose and use case
  - Installation/dependencies
  - Example usage with sample output
-  Follow security best practices (no hardcoded secrets, input validation)
-  Prefer Python 3 or Bash (widely available in CTF environments)

**Example structure**:
```
toolkit/
└── auto-sqli/
    ├── README.md
    ├── auto_sqli.py
    ├── requirements.txt
    └── examples/
        └── demo.gif
```

---

###  Original Challenges

Create challenges for internal training or university CTF events:

**Submission checklist**:
- [ ] Challenge files (source code, binaries, Dockerfile if needed)
- [ ] `challenge.yml` metadata (category, difficulty, description)
- [ ] `solution/` directory with:
  - Step-by-step solution guide
  - Exploit script
  - Flag format example (`FLAG{example_redacted}`)
- [ ] Dockerfile or setup script for easy deployment
- [ ] Test that challenge is solvable by another team member

⚠️ **Security review required** before deployment to any public-facing environment.

---

##  Contribution Workflow

1. **Fork** the target repository
2. **Create a branch** with descriptive name:
   ```bash
   git checkout -b feat/add-uoft-ctf-writeup
   # or
   git checkout -b fix/training-web-xss-typo
   ```
3. **Make your changes** following style guidelines below
4. **Test locally**:
   - Scripts: Verify they run in a clean environment
5. **Commit with descriptive message**:
   ```bash
   git commit -m "feat(writeups): add UofTCTF 2026 web/crypto challenges"
   ```
6. **Push to your fork**:
   ```bash
   git push origin feat/add-uoft-ctf-writeup
   ```
7. **Open a Pull Request** against the `main` branch with:
   - Clear title following [Conventional Commits](https://www.conventionalcommits.org/)
   - Description of changes
   - Screenshots for UI/training changes
   - Link to related issue (if applicable)

---

##  Style Guidelines

### Markdown & Documentation
- Use **sentence case** for headings (`## Web Exploitation` not `## WEB EXPLOITATION`)
- Code blocks must specify language for syntax highlighting:
  ````markdown
  ```python
  print("Hello world")
  ```
  ````
- Redact flags: `FLAG{redacted_example}` or `UofT{...}`

### Python Scripts
```python
# ✅ Good
def exploit(target: str, port: int = 80) -> bool:
    """Exploit CVE-XXXX-XXXX via path traversal"""
    try:
        # Implementation
        return True
    except Exception as e:
        logging.error(f"Exploit failed: {e}")
        return False

# ❌ Avoid
def pwn(ip,port=80):
    try:
        # no error handling
        return 1
    except:
        return 0
```

### Git Commit Messages
Follow [Conventional Commits](https://www.conventionalcommits.org/):
```
feat(writeups): add ASIS CTF 2025 crypto challenges
fix(training): correct XSS payload in web module
docs(toolkit): add README for auto-reverser script
chore: update dependencies in requirements.txt
```

---

##  Security Policy

### Responsible Disclosure
If you discover a **security vulnerability** in our infrastructure or tools:

1. **Do not** create a public issue or PR
2. **Do not** share details publicly
3. Email the contributing member

### Competition Integrity
- Never share flags/solutions during active competitions
- Never automate flag submission against live CTF platforms without explicit permission
- Respect rate limits and competition terms of service

---

##  Getting Help

| Channel | Purpose | Contact |
|---------|---------|---------|
| **GitHub Issues** | Bug reports, feature requests | Open in relevant repo |
| **Email** | Sensitive matters, security reports | Email any core team member |

---

## Recognition

Contributors receive:
-  GitHub contributor status on relevant repositories
-  Attribution in writeup author lists
-  Invitation to team practice sessions
-  Priority consideration for competition lineups
-  Featured on our [Contributors page](CONTRIBUTORS.md) *(coming soon)*

All significant contributors will be acknowledged in our annual report to UM6P College of Computing.

---

##  License

By contributing, you agree that your work will be licensed under the [MIT License](LICENSE) unless otherwise specified in the file header.

---

> 💙 *"Alone we can do so little; together we can do so much."* — Helen Keller  
> Thank you for helping Mi9chada represent Morocco on the global cybersecurity stage!
