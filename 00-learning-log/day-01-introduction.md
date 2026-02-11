# Day 1: Introduction to GRC

**Date:** [11th February 2026]  
**Time Spent:** 1.5 hours  
**Source:** Simply Cyber's Gerald Auger, PhD (YouTube)  
**Topic Folder:** [01-introduction](../01-introduction/)

---

## 🎯 Today's Learning Objectives

- [x] Understand what GRC stands for
- [x] Learn the three pillars of GRC
- [x] Understand enterprise applicability
- [x] Learn key NIST publications

---

## 📝 Key Concepts Learned

### What is GRC?

**GRC** = **G**overnance + **R**isk + **C**ompliance

&gt; GRC is primarily for **middle-sized and large enterprises**. Small businesses typically don't have the scale or resources for formal GRC programs.

### 1. Governance

**Definition:** How to govern end users, assets, and the company through rules, policies, and procedures.

**Key Insight:** It's not just documentation—it's an **organizational cultural impact**. How you implement matters as much as what you implement.

**Components:**
- Rules
- Policies
- Procedures
- Cultural integration

### 2. Compliance

**Definition:** Complying with requirements and regulations that are required.

**Nature:** A **minimum set of standards** that a company must comply with to:
- Meet legal/regulatory requirements
- Avoid restrictions (fines, penalties, operational limitations)

&gt; Compliance is the **floor**, not the ceiling.

### 3. Risk (The Largest Part)

**Definition:** Assessing and managing uncertainty that could impact organizational objectives.

**Two Approaches:**

| Approach | Description | Pros | Cons | Best For |
|----------|-------------|------|------|----------|
| **Qualitative** | Subjective assessment using categories (High/Med/Low) | Easier to implement, intuitive | Hard to measure, inconsistent | Smaller orgs, initial assessments |
| **Quantitative** | Numerical analysis using data ($ value, percentages) | Objective, measurable, defensible | Requires established metrics, complex | Mature organizations, board reporting |

&gt; ⚠️ **Critical Truth:** One can never be 100% secure. Ever. Risk management is about **optimization**, not elimination.

---

## 📚 Resources Referenced

### NIST Publications (Special Mention)

| Publication | Title | Purpose |
|-------------|-------|---------|
| **NIST 800-39** | Managing Information Security Risk | Shows **how to implement** an organization's risk management framework |
| **NIST 800-37** | Risk Management Framework for Information Systems | **The** risk management framework (RMF) |

---

## 🔍 Deep Dive: Audits & Remediation

**The Complete Process:**


Perfect! VS Code makes this much smoother. Let me give you the Windows + VS Code optimized workflow.
🎓 GitHub Mastery: Windows + VS Code Edition
Part 1: Install Everything (One-Time Setup)
Step 1.1: Install Git for Windows

    Download from git-scm.com
    Run installer, use these settings:
        ✅ "Git from the command line and also from 3rd-party software" (PATH option)
        ✅ "Use the OpenSSL library"
        ✅ "Checkout Windows-style, commit Unix-style line endings"
        ✅ "Use MinTTY" (the terminal)
        ✅ "Enable file system caching"
    Finish installation

Verify in VS Code:

    Open VS Code
    Press Ctrl + ` (backtick, above Tab key) to open terminal
    Type: git --version
    Should show: git version 2.x.x

Step 1.2: Configure Git (In VS Code Terminal)
bash
Copy

# Set your identity (use your GitHub email)
git config --global user.name "Your Full Name"
git config --global user.email "your-github-email@example.com"
git config --global init.defaultBranch main

# Set VS Code as your default editor
git config --global core.editor "code --wait"

# Verify
git config --list

Step 1.3: Connect to GitHub with SSH
In VS Code terminal:
bash
Copy

# Generate SSH key
ssh-keygen -t ed25519 -C "your-github-email@example.com"

# Press Enter 3 times (accept defaults)

# Start SSH agent
eval "$(ssh-agent -s)"

# Add key
ssh-add ~/.ssh/id_ed25519

# Copy key to clipboard
cat ~/.ssh/id_ed25519.pub | clip

Add to GitHub:

    Go to GitHub → Profile (top right) → Settings
    Left sidebar → SSH and GPG keys
    New SSH key
    Title: My Windows Laptop
    Paste key (Ctrl+V)
    Add SSH key

Test it:
bash
Copy

ssh -T git@github.com
# Type "yes" if asked
# Should see: "Hi username! You've successfully authenticated..."

Part 2: VS Code Setup for GitHub
Step 2.1: Install Extensions
Click the Extensions icon (left sidebar, looks like squares) or press Ctrl+Shift+X
Install these:

    GitLens (by GitKraken) - Supercharges git
    Markdown All in One (by Yu Zhang) - Preview and shortcuts
    markdownlint (by David Anson) - Linting

Step 2.2: Configure VS Code Settings
Press Ctrl+, (comma) to open settings
Search and set these:
Table
Copy
Setting	Value	Why
files.autoSave	afterDelay	Auto-saves your work
git.enableSmartCommit	✅ Checked	Easier commits
git.confirmSync	Uncheck	Faster push/pull
editor.formatOnSave	✅ Checked	Clean formatting
Part 3: Create Repository (Web + VS Code Hybrid)
Step 3.1: Create on GitHub

    Go to github.com
    Click "+" → New repository
    Name: grc-learning-journey
    Description: Daily GRC learning documentation - structured by topic
    Public ✅
    UNCHECK "Add a README"
    CHECK "Add .gitignore" → Select Node
    CHECK "MIT License"
    Create repository

Step 3.2: Clone to Your Computer (VS Code)
Method A: VS Code GUI

    In VS Code: Ctrl+Shift+P (Command Palette)
    Type: Git: Clone
    Paste: git@github.com:YOUR-USERNAME/grc-learning-journey.git
    Choose folder: C:\Users\YourName\Documents\ (or wherever)
    Click Open when prompted

Method B: Terminal
bash
Copy

# In VS Code terminal (Ctrl+`)
cd C:/Users/YourName/Documents
git clone git@github.com:YOUR-USERNAME/grc-learning-journey.git
cd grc-learning-journey
code .

You now have VS Code open with your repository!
Part 4: Create Folder Structure (VS Code)
Step 4.1: Create Folders
In VS Code Explorer (left sidebar):

    Hover over empty space below your files
    Click "New Folder" icon
    Create these folders one by one:

plain
Copy

00-learning-log/
01-introduction/
02-governance/
02-governance/policies/
03-risk-management/
04-compliance/
05-frameworks/
05-frameworks/nist/
05-frameworks/iso/
06-audit-assessment/
07-tools/
resources/
resources/templates/

VS Code Pro Tip: Type 02-governance/policies/ and VS Code will create both folder and subfolder automatically!
Step 4.2: Create .gitkeep Files
We need files so Git tracks empty folders:

    Right-click 00-learning-log folder → New File
    Name: .gitkeep
    Repeat for every folder (or use terminal method below)

Faster Method - VS Code Terminal:
bash
Copy

# In VS Code terminal (Ctrl+`)
touch 00-learning-log/.gitkeep 01-introduction/.gitkeep 02-governance/.gitkeep 02-governance/policies/.gitkeep 03-risk-management/.gitkeep 04-compliance/.gitkeep 05-frameworks/.gitkeep 05-frameworks/nist/.gitkeep 05-frameworks/iso/.gitkeep 06-audit-assessment/.gitkeep 07-tools/.gitkeep resources/.gitkeep resources/templates/.gitkeep

Part 5: Create Your Files (VS Code)
Step 5.1: Create README.md

    Right-click in empty space → New File
    Name: README.md
    Paste this content:

Markdown
Copy
Code Preview

# 🛡️ GRC Learning Journey

> Daily documentation of my journey from zero to GRC professional.
> Structured by topic. Built for retention. Designed for portfolio.

---

## 📊 Progress Dashboard

| Day | Date | Topic | Status | Learning Log |
|:---:|:----:|-------|:------:|:------------:|
| 1 | TBD | What is GRC? | 🔄 In Progress | [Day 1](./00-learning-log/day-01-introduction.md) |

**Legend:** 🔄 In Progress | ✅ Complete | ⏸️ Paused | 📅 Planned

---

## 🗂️ Topic Structure

grc-learning-journey/
├── 00-learning-log/          # Daily entries (chronological)
├── 01-introduction/          # GRC fundamentals, concepts
├── 02-governance/            # Policies, procedures, culture
│   └── policies/             # Policy templates & examples
├── 03-risk-management/       # Risk assessment & treatment
├── 04-compliance/            # Regulations & standards
├── 05-frameworks/            # Implementation frameworks
│   ├── nist/                 # NIST 800-37, 800-39, CSF
│   └── iso/                  # ISO 27001, 27002, etc.
├── 06-audit-assessment/      # Auditing, testing, reporting
├── 07-tools/                 # GRC platforms, automation
└── resources/                # Templates, cheatsheets, links
└── templates/            # Reusable document templates
plain
Copy


---

## 🎯 Current Focus

**Day 1:** Understanding GRC fundamentals - Governance, Risk, and Compliance pillars.

---

## 📝 Latest Updates

- **Day 1:** Introduction to GRC concepts, NIST publications overview

---

## 🔗 Quick Navigation

| Topic | Path |
|-------|------|
| Daily Logs | [`00-learning-log/`](./00-learning-log/) |
| Introduction | [`01-introduction/`](./01-introduction/) |
| Governance | [`02-governance/`](./02-governance/) |
| Risk Management | [`03-risk-management/`](./03-risk-management/) |
| Compliance | [`04-compliance/`](./04-compliance/) |
| Frameworks | [`05-frameworks/`](./05-frameworks/) |

---

## 💡 Why This Exists

1. **Knowledge Retention:** Writing = learning twice
2. **Portfolio Proof:** Demonstrates structured thinking to employers
3. **Future Reference:** GRC concepts build on each other - I'll need to review
4. **Community:** Public repo helps others learning GRC

---

## 🛠️ How I Work

- **Daily updates:** Every day I learn, I document
- **Topic-organized:** Content lives in topic folders, not scattered
- **Hybrid workflow:** VS Code for serious work, web for quick fixes
- **Conventional commits:** Professional commit message standards

---

*Started: [Date]*  
*Last Updated: [Date]*  
*Learning Source: Simply Cyber, NIST Publications, Industry Standards*

    Save: Ctrl+S

Step 5.2: Create Daily Log Template

    Right-click resources/templates/ → New File
    Name: daily-log-template.md
    Paste this (your reusable template):

Markdown
Copy
Code Preview

# Day {{DAY_NUMBER}}: {{TOPIC_TITLE}}

**Date:** {{DATE}}  
**Time Spent:** {{HOURS}} hours  
**Source:** {{SOURCE_NAME}} ({{SOURCE_TYPE}})  
**Topic Folder:** [{{TOPIC_PATH}}](../{{TOPIC_FOLDER}}/)

---

## 🎯 Today's Learning Objectives

- [ ] {{OBJECTIVE_1}}
- [ ] {{OBJECTIVE_2}}
- [ ] {{OBJECTIVE_3}}

---

## 📝 Key Concepts Learned

### {{CONCEPT_1}}

{{Description of first major concept}}

**Key Points:**
- Point 1
- Point 2
- Point 3

> 💡 **Key Quote:** {{Important quote or insight}}

### {{CONCEPT_2}}

{{Description of second concept}}

| Aspect | Details |
|--------|---------|
| Item 1 | Description |
| Item 2 | Description |

---

## 📚 Resources Referenced

1. **{{RESOURCE_1}}** — {{Description}}
   - Link: {{URL}}
2. **{{RESOURCE_2}}** — {{Description}}
   - Link: {{URL}}

---

## 🔍 Deep Dive: {{SUB_TOPIC}}

{{Detailed exploration of one specific area}}

**Process/Steps:**
1. Step one
2. Step two
3. Step three

---

## ❓ Critical Questions & Answers

| Question | My Answer | Confidence |
|----------|-----------|------------|
| {{Q1}} | {{A1}} | High/Med/Low |
| {{Q2}} | {{A2}} | High/Med/Low |

---

## 🎯 Key Takeaways

1. {{Takeaway 1}}
2. {{Takeaway 2}}
3. {{Takeaway 3}}

---

## ⚠️ Common Misconceptions Clarified

- **Misconception:** {{Wrong idea}}
- **Reality:** {{Correct understanding}}

---

## 🔗 Connections to Previous Days

- [Day {{PREV_DAY}}](./day-{{PREV_DAY_ZERO_PADDED}}-{{PREV_TOPIC}}.md): {{Connection}}
- Related Topic: [{{TOPIC}}](../{{FOLDER}}/{{FILE}}.md)

---

## 🤔 Questions for Future Research

- [ ] {{QUESTION_1}}
- [ ] {{QUESTION_2}}

---

## 🎯 Action Items

- [ ] {{ACTION_1}}
- [ ] {{ACTION_2}}

---

## 📝 Raw Notes (Unprocessed)

{{Quick notes, timestamps, messy thoughts during learning}}

---

**Next:** Day {{NEXT_DAY}} - {{NEXT_TOPIC}}

---

## 🔗 Related Files

- [Detailed Notes: {{TOPIC}}](../{{TOPIC_FOLDER}}/{{DETAILED_FILE}}.md)
- [Template Used](../resources/templates/daily-log-template.md)

    Save: Ctrl+S

Step 5.3: Create Day 1 Learning Log

    Right-click 00-learning-log/ → New File
    Name: day-01-introduction.md
    Paste this (already filled for Day 1):

Markdown
Copy
Code Preview

# Day 1: Introduction to GRC

**Date:** [Today's Date]  
**Time Spent:** 1.5 hours  
**Source:** Simply Cyber's Gerald Auger, PhD (YouTube)  
**Topic Folder:** [01-introduction](../01-introduction/)

---

## 🎯 Today's Learning Objectives

- [x] Understand what GRC stands for
- [x] Learn the three pillars of GRC
- [x] Understand enterprise applicability
- [x] Learn key NIST publications

---

## 📝 Key Concepts Learned

### What is GRC?

**GRC** = **G**overnance + **R**isk + **C**ompliance

> GRC is primarily for **middle-sized and large enterprises**. Small businesses typically don't have the scale or resources for formal GRC programs.

### 1. Governance

**Definition:** How to govern end users, assets, and the company through rules, policies, and procedures.

**Key Insight:** It's not just documentation—it's an **organizational cultural impact**. How you implement matters as much as what you implement.

**Components:**
- Rules
- Policies
- Procedures
- Cultural integration

### 2. Compliance

**Definition:** Complying with requirements and regulations that are required.

**Nature:** A **minimum set of standards** that a company must comply with to:
- Meet legal/regulatory requirements
- Avoid restrictions (fines, penalties, operational limitations)

> Compliance is the **floor**, not the ceiling.

### 3. Risk (The Largest Part)

**Definition:** Assessing and managing uncertainty that could impact organizational objectives.

**Two Approaches:**

| Approach | Description | Pros | Cons | Best For |
|----------|-------------|------|------|----------|
| **Qualitative** | Subjective assessment using categories (High/Med/Low) | Easier to implement, intuitive | Hard to measure, inconsistent | Smaller orgs, initial assessments |
| **Quantitative** | Numerical analysis using data ($ value, percentages) | Objective, measurable, defensible | Requires established metrics, complex | Mature organizations, board reporting |

> ⚠️ **Critical Truth:** One can never be 100% secure. Ever. Risk management is about **optimization**, not elimination.

---

## 📚 Resources Referenced

### NIST Publications (Special Mention)

| Publication | Title | Purpose |
|-------------|-------|---------|
| **NIST 800-39** | Managing Information Security Risk | Shows **how to implement** an organization's risk management framework |
| **NIST 800-37** | Risk Management Framework for Information Systems | **The** risk management framework (RMF) |

---

## 🔍 Deep Dive: Audits & Remediation

**The Complete Process:**

┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────────┐
│  Audit  │───→│  Test   │───→│  Score  │───→│   Identify  │───→│ Action Plan │───→│ Report to Mgmt  │
│         │    │         │    │         │    │  Weaknesses │    │             │    │                 │
└─────────┘    └─────────┘    └─────────┘    └─────────────┘    └─────────────┘    └─────────────────┘


**Why Testing is Critical:**
- Controls might be **misconfigured** (technical failure)
- End users might be **intentionally ignoring** them (human failure)
- Documentation might not match **reality** (process failure)

---

## ❓ Critical Questions & Answers

| Question | My Answer | Confidence |
|----------|-----------|------------|
| Is GRC only for cybersecurity? | No, it's enterprise-wide, but cyber is a major component | High |
| Can small companies do GRC? | Yes, but scaled down. Formal GRC is for mid-large orgs | Medium |
| Which is better: qualitative or quantitative risk? | Depends on maturity. Start qualitative, evolve to quantitative | Medium |

---

## 🎯 Key Takeaways

1. **Policy Quantity ≠ Quality**
   - Don't write 400 policies for compliance theater
   - Write **minimum viable policies** that matter to your organization
   - Communicate them throughout the organization
   - **Top management buy-in is critical** (this is where most programs fail)

2. **Risk is Inevitable**
   - 100% security is impossible
   - Focus on risk **optimization**, not elimination
   - Business must accept some risk to function

3. **Frameworks Exist for a Reason**
   - NIST 800-37 and 800-39 provide roadmaps
   - Don't reinvent the wheel

---

## ⚠️ Common Misconceptions Clarified

- **Misconception:** Compliance = Security
- **Reality:** Compliance is the **minimum** bar. You can be compliant and still be insecure.

- **Misconception:** More policies = Better governance
- **Reality:** Unread, unenforced policies are worse than no policies. They create false confidence.

---

## 📝 Raw Notes

- GRC = Governance, Risk, Compliance
- Gerald Auger - Simply Cyber YouTube
- Middle/large enterprises mainly
- Governance = rules, policies, procedures + culture
- Compliance = minimum standards, avoid restrictions
- Risk = biggest part, qual vs quant
- NIST 800-39 = how to implement RMF
- NIST 800-37 = the RMF itself
- Audit → test → score → find weaknesses → action plan → report
- Don't write 400 policies
- Write few important ones, communicate, get mgmt buy-in

---