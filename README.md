# n8n Quick Reference

Minimal, beginner-friendly notes for future revision. Scope kept tight to what we covered.

## Table of Contents
- [1. Automation vs AI Automation](#1-automation-vs-ai-automation)
- [2. Types of Automation](#2-types-of-automation)
- [3. About n8n](#3-about-n8n)
- [4. Hosting Options](#4-hosting-options)
- [5. Local Setup (Recommended for Learning)](#5-local-setup-recommended-for-learning)
- [6. Self-Host on Hostinger VPS](#6-self-host-on-hostinger-vps)
- [7. Workspace Overview](#7-workspace-overview)
- [8. Inside a Workflow](#8-inside-a-workflow)
- [9. Workflow Settings](#9-workflow-settings)
- [10. Keyboard Shortcuts](#10-keyboard-shortcuts)
- [11. Quick Memory Maps](#11-quick-memory-maps)
- [12. Useful Links](#12-useful-links)

---

## 1. Automation vs AI Automation

| Topic | Automation | AI Automation |
|---|---|---|
| Meaning | Follows fixed rules | Uses AI to understand, decide, or generate |
| Logic | `if this -> do that` | context-based |
| Best for | repetitive tasks | content-heavy or judgment-heavy tasks |
| Example in n8n | New form entry -> save to sheet -> send email | Read email -> classify with LLM -> route reply |

### Simple memory line
- **Automation** = rules
- **AI Automation** = rules + intelligence

---

## 2. Types of Automation

### 2.1 ETL Automation
**ETL = Extract -> Transform -> Load**

Example:
- Read Excel / DB / API
- Clean or map fields
- Load into another system

Good for:
- data migration
- reporting
- system-to-system sync

### 2.2 UI Automation
Automates screen-level actions when proper APIs are not available.

Example:
- open website
- fill form
- click button
- capture result

Use carefully because UI-based automation is usually more fragile than API-based automation.

### 2.3 API Automation
Most common and preferred in n8n.

Example:
- receive webhook
- call API
- transform response
- send to another app

Best when:
- system has API
- reliability matters
- speed matters

---

## 3. About n8n

### What is n8n?
n8n is a **fair-code workflow automation platform** with visual drag-and-drop building, code options when needed, and AI features built into the platform.

### Why people like n8n
- open source / fair-code style ecosystem
- low-code / no-code feel
- flexible: visual + code together
- lower cost when self-hosted
- good for APIs, ETL, webhooks, AI workflows

### Is n8n same as LangChain?
No.

- **n8n** = automation platform
- **LangChain** = framework/library for building LLM apps

You can connect AI tools inside n8n, but n8n itself is not LangChain.

### n8n vs Zapier / Make / Pabbly

| Tool | Best known for | n8n edge |
|---|---|---|
| Zapier | easiest SaaS automation | more control, self-hosting |
| Make | very visual scenarios | open ecosystem + flexibility |
| Pabbly | budget-friendly SaaS | more developer-level flexibility |
| n8n | flexible automation + AI + self-hosting | strongest control/cost mix for technical users |

---

## 4. Hosting Options

| Option | Best for | Cost feel | 24/7? | Notes |
|---|---|---|---|---|
| Localhost | learning and testing | lowest | No | runs on your laptop/desktop |
| Self-hosted VPS | serious personal/prod use | medium | Yes | you manage server |
| n8n Cloud | easiest production use | highest | Yes | official managed service |

### Memory tip
- **Local** -> learn
- **VPS** -> control
- **Cloud** -> convenience

---

## 5. Local Setup (Recommended for Learning)

Official install docs: https://docs.n8n.io/hosting/installation/

### Step 1: Install Node.js
Go to Node.js official site and install the current supported LTS version.

### Step 2: Verify Node.js
```bash
node -v
```

### Step 3: Verify npm
```bash
npm -v
```

### Step 4: Install n8n globally
Recommended:
```bash
npm install n8n -g
```

Temporary method, not preferred for regular use:
```bash
npx n8n
```

### Step 5: Start n8n
```bash
n8n start
```

### Step 6: Open in browser
```bash
http://localhost:5678
```

### Step 7: Create your owner account
On first launch:
- create login
- enter workspace
- start building workflows

### Why global install is easier for beginners
- one-time setup
- faster reuse
- cleaner habit for repeated local practice

---

## 6. Self-Host on Hostinger VPS

Official self-hosting docs: https://docs.n8n.io/hosting/

### When to choose VPS
Choose VPS when:
- you want 24/7 workflows
- your laptop should not stay on
- you want public webhooks
- you want lower long-term cost than managed cloud

### Suggested Hostinger starting point
A practical starter choice is **KVM 2** because Hostinger currently lists it with **1 vCPU, 4 GB RAM, 50 GB NVMe storage, and 4 TB bandwidth** on its India pricing page.

If you expect heavier usage, step up to **KVM 4**.

### Step-by-step setup on Hostinger

#### Step 1: Buy VPS
- open Hostinger VPS page
- choose KVM plan
- complete purchase

#### Step 2: Open VPS panel
Collect:
- server IP
- root username
- root password

#### Step 3: Connect through SSH
Linux / Mac:
```bash
ssh root@YOUR_SERVER_IP
```

Windows:
- use Terminal with SSH, or PuTTY

#### Step 4: Update server
```bash
apt update && apt upgrade -y
```

#### Step 5: Install Node.js and npm
Follow Node.js install steps for Ubuntu from official docs, then verify:
```bash
node -v
npm -v
```

#### Step 6: Install n8n
```bash
npm install n8n -g
```

#### Step 7: Start once for testing
```bash
n8n start
```

#### Step 8: Make it run continuously
Common production pattern:
- use **Docker** or **systemd**
- place n8n behind a reverse proxy
- add domain + HTTPS

#### Step 9: Set timezone to India
Use:
```bash
export GENERIC_TIMEZONE=Asia/Kolkata
```

#### Step 10: Secure it
Minimum:
- strong login
- HTTPS
- backup
- firewall
- regular updates

---

## 7. Workspace Overview

When you open n8n workspace, focus on these sections:

### Production Executions
How many automatic runs happened in active workflows.

### Failed Executions
Shows failed runs that need attention.

### Failure Rate
Quick health metric:
- lower is better

### Time Saved
Estimate of time automation saved.

### Run Time (Average)
Average execution speed.

### Templates
Ready-made workflows to learn faster.

### Insights
Analytics / overview area for usage and performance.

### Create Workflow
Main entry to start your own automation.

---

## 8. Inside a Workflow

### Add Nodes
Ways to add:
- click **+**
- press **N**
- search node name

### Sticky Notes
Good practice:
- explain sections
- note assumptions
- mark TODOs
- help future-you after 1 year

### Node options to remember
- execute
- deactivate
- delete
- rename
- duplicate

### Data views inside node execution
Common views:
- **Schema**
- **Table**
- **JSON**

### Is n8n JSON formatted?
Yes. Workflows are stored in JSON format, and node data is commonly viewed as JSON too.

### Node documentation
n8n provides docs for built-in nodes:
https://docs.n8n.io/integrations/builtin/

---

## 9. Workflow Settings

Open workflow -> top-right menu -> **Settings**

### Execution logic
Use **v1** for new workflows.

Quick comparison:
- **v0** = older legacy execution behavior for pre-1.0 workflows
- **v1** = current recommended execution order

### Error Workflow
Useful when you want one workflow to handle failures from another workflow.

Example:
- main workflow fails
- error workflow sends alert / log / email

### Timezone
For India, set:
- **Asia/Kolkata**

This is important for:
- schedule triggers
- logs
- date/time consistency

---

## 10. Keyboard Shortcuts

Official shortcuts docs: https://docs.n8n.io/keyboard-shortcuts/

| Shortcut | Use |
|---|---|
| `N` | open nodes panel |
| `Ctrl/Cmd + S` | save workflow |
| `Ctrl/Cmd + Z` | undo |
| `Ctrl/Cmd + Shift + Z` | redo |
| `Ctrl/Cmd + Enter` | execute workflow |
| `Del` | delete selected node |
| `Ctrl/Cmd + C` | copy |
| `Ctrl/Cmd + V` | paste |

### Extra editor habits
- double-click or use rename action for better node names
- use sticky notes early
- keep flow left to right
- test small blocks, not only full workflow

---

## 11. Quick Memory Maps

### 11.1 Big Picture
```text
Trigger -> Process -> Decision -> Action -> Monitor
```

### 11.2 Hosting Choice Map
```text
Want to learn only?
  -> Localhost

Want 24/7 + control?
  -> VPS self-host

Want easiest managed setup?
  -> n8n Cloud
```

### 11.3 Beginner Build Flow
```text
Open n8n
  -> Create workflow
  -> Add trigger
  -> Add action nodes
  -> Test node by node
  -> Add sticky notes
  -> Save
  -> Activate
  -> Monitor executions
```

---

## 12. Useful Links

- n8n docs: https://docs.n8n.io/
- Hosting docs: https://docs.n8n.io/hosting/
- Installation docs: https://docs.n8n.io/hosting/installation/
- Built-in node docs: https://docs.n8n.io/integrations/builtin/
- Keyboard shortcuts: https://docs.n8n.io/keyboard-shortcuts/
- Workflow settings: https://docs.n8n.io/workflows/settings/
- Execution order: https://docs.n8n.io/flow-logic/execution-order/

---

## Final Revision Notes

### What to remember in one minute
- n8n is for workflow automation
- AI automation = n8n + intelligence/LLM layer
- API automation is usually best
- use localhost first
- use VPS when you need 24/7
- set timezone to `Asia/Kolkata`
- use execution order **v1**
- document with sticky notes
- monitor failed executions regularly
