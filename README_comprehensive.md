# 📘 n8n Comprehensive Guide for Beginners

> A complete, beginner-friendly guide to understanding and mastering n8n automation platform. Perfect for revisiting after months or years to quickly refresh your knowledge.

---

## 📑 Table of Contents

1. [Introduction to n8n](#1-introduction-to-n8n)
   - [What is n8n?](#what-is-n8n)
   - [Key Features](#key-features)
   - [Why Choose n8n?](#why-choose-n8n)

2. [Automation vs AI Automation](#2-automation-vs-ai-automation)
   - [Traditional Automation](#traditional-automation)
   - [AI Automation with n8n](#ai-automation-with-n8n)
   - [Key Differences](#key-differences)

3. [Types of Automation](#3-types-of-automation)
   - [ETL Automation](#etl-automation)
   - [UI Automation](#ui-automation)
   - [API Automation](#api-automation)

4. [About n8n Platform](#4-about-n8n-platform)
   - [Open Source Advantage](#open-source-advantage)
   - [Drag and Drop Interface](#drag-and-drop-interface)
   - [Cost Effectiveness](#cost-effectiveness)
   - [Flexibility and Integration](#flexibility-and-integration)
   - [Comparison with Competitors](#comparison-with-competitors)

5. [n8n Hosting Options](#5-n8n-hosting-options)
   - [Local Host Setup](#local-host-setup)
   - [Self-Hosted Cloud (VPS)](#self-hosted-cloud-vps)
   - [Production Cloud (n8n.io)](#production-cloud-n8nio)
   - [Hosting Comparison Table](#hosting-comparison-table)

6. [Local Setup Guide (Step-by-Step)](#6-local-setup-guide-step-by-step)
   - [Prerequisites](#prerequisites)
   - [Installation Steps](#installation-steps)
   - [Troubleshooting](#troubleshooting)

7. [Self-Hosting with Hostinger (KVM VPS)](#7-self-hosting-with-hostinger-kvm-vps)
   - [Choosing the Right Plan](#choosing-the-right-plan)
   - [VPS Setup Steps](#vps-setup-steps)
   - [n8n Installation on VPS](#n8n-installation-on-vps)

8. [n8n Workspace Overview](#8-n8n-workspace-overview)
   - [Dashboard Metrics](#dashboard-metrics)
   - [Templates](#templates)
   - [Insights](#insights)

9. [Workflow Creation](#9-workflow-creation)
   - [Adding Nodes](#adding-nodes)
   - [Using Sticky Notes](#using-sticky-notes)
   - [Node Properties](#node-properties)
   - [Data Formats](#data-formats)
   - [Node Documentation](#node-documentation)

10. [Workflow Settings](#10-workflow-settings)
    - [Execution Logic (v0 vs v1)](#execution-logic-v0-vs-v1)
    - [Error Workflow](#error-workflow)
    - [Timezone Configuration](#timezone-configuration)

11. [n8n Keyboard Shortcuts](#11-n8n-keyboard-shortcuts)
    - [Essential Shortcuts](#essential-shortcuts)
    - [Productivity Tips](#productivity-tips)

12. [Workflow Editor Features](#12-workflow-editor-features)
    - [Editor Tab](#editor-tab)
    - [Executions Tab](#executions-tab)
    - [Evaluations Tab](#evaluations-tab)

13. [Best Practices](#13-best-practices)
14. [Common Use Cases](#14-common-use-cases)
15. [Resources and Links](#15-resources-and-links)

---

## 1. Introduction to n8n

### What is n8n?

n8n (pronounced "n-eight-n") is a powerful workflow automation tool that helps you connect different apps and services together. Think of it as a smart assistant that can handle repetitive tasks automatically, saving you time and reducing errors.

**Simple Example**: Instead of manually copying data from Gmail to Google Sheets every day, n8n can do it automatically whenever a new email arrives.

### Key Features

- ✅ **Visual Workflow Builder**: No coding required (though you can code if you want)
- ✅ **400+ Integrations**: Connect with popular apps and services
- ✅ **Self-Hostable**: Your data stays with you
- ✅ **Free and Open Source**: Community-driven development
- ✅ **Powerful Data Transformation**: Built-in tools to manipulate data

### Why Choose n8n?

1. **Privacy First**: Unlike cloud-only services, you control where your data lives
2. **Cost Effective**: Free for self-hosting, no per-task pricing
3. **Extensible**: Can be customized to fit any workflow
4. **Active Community**: Regular updates and helpful community support

---

## 2. Automation vs AI Automation

### Traditional Automation

Traditional automation follows **predefined rules** and **fixed logic**. It's like a recipe that you follow step-by-step every time.

**Characteristics**:
- Rule-based decision making
- If-then-else conditions
- No learning capability
- Same output for same input every time
- Predictable behavior

**Example**: 
```
IF new email arrives 
AND email contains "invoice"
THEN save attachment to Google Drive
```

### AI Automation with n8n

AI automation incorporates **intelligent decision-making** and can **adapt** based on context and content.

**Characteristics**:
- Natural language processing
- Context-aware actions
- Can handle ambiguity
- Learning from patterns
- Dynamic responses

**Example with AI**:
```
WHEN new email arrives
USE AI to understand the email content
CLASSIFY the email (invoice, query, complaint, etc.)
BASED ON classification, route to appropriate workflow
GENERATE intelligent response using AI
```

### Key Differences

| Aspect | Traditional Automation | AI Automation |
|--------|----------------------|---------------|
| **Logic** | Fixed rules | Adaptive intelligence |
| **Decision Making** | Predefined conditions | Context-aware |
| **Learning** | No learning | Can improve over time |
| **Complexity** | Simple workflows | Complex reasoning |
| **Setup** | Easier to configure | Requires AI integration |
| **Use Cases** | Repetitive tasks | Content understanding |

**When to Use Each**:
- **Traditional**: Data transfer, scheduled tasks, simple triggers
- **AI**: Email classification, content generation, sentiment analysis

---

## 3. Types of Automation

### ETL Automation

**ETL = Extract, Transform, Load**

This is all about moving and transforming data between different systems.

**What it does**:
1. **Extract**: Get data from source (database, API, file)
2. **Transform**: Clean, format, or modify the data
3. **Load**: Put data into destination system

**Real-World Examples**:
- Syncing customer data between CRM and marketing tools
- Migrating data from old database to new one
- Combining data from multiple sources into a data warehouse
- Converting CSV files to database entries

**n8n Nodes for ETL**:
- Database nodes (MySQL, PostgreSQL, MongoDB)
- Spreadsheet nodes (Google Sheets, Excel)
- Transform nodes (Set, Function, Code)

### UI Automation

**User Interface Automation**

Automates tasks that normally require human interaction with websites or applications.

**What it does**:
- Fills out forms automatically
- Clicks buttons and navigates websites
- Extracts data from web pages (scraping)
- Performs repetitive UI tasks

**Real-World Examples**:
- Automatically filling out registration forms
- Scraping product prices from e-commerce sites
- Testing web applications
- Generating reports from web dashboards

**n8n Capabilities**:
- HTTP Request node for API interactions
- HTML Extract node for web scraping
- Browser automation via Puppeteer

### API Automation

**Application Programming Interface Automation**

Connects different software applications through their APIs.

**What it does**:
- Sends and receives data between apps
- Triggers actions in other applications
- Listens for webhooks and events
- Synchronizes data across platforms

**Real-World Examples**:
- When someone fills a form, create a CRM contact
- When a payment succeeds, send a thank you email
- When inventory is low, notify on Slack
- Sync calendar events across multiple platforms

**API Types in n8n**:
- **REST APIs**: Most common (HTTP Request node)
- **GraphQL**: Flexible queries
- **Webhooks**: Real-time triggers
- **SOAP**: Legacy systems

---

## 4. About n8n Platform

### Open Source Advantage

n8n is **fair-code** licensed, which means:

- ✅ Source code is publicly available
- ✅ You can self-host for free
- ✅ Community can contribute features
- ✅ Transparent development
- ✅ No vendor lock-in

**Benefits for You**:
1. **Trust**: You can see exactly what the software does
2. **Customization**: Modify it for your specific needs
3. **Cost**: No mandatory subscriptions
4. **Community**: Learn from others' workflows

### Drag and Drop Interface

**Low-Code / No-Code Platform**

n8n provides a visual interface where you can:
- Drag nodes onto canvas
- Connect them with lines
- Configure settings through forms
- Test workflows instantly

**Is it related to LangChain?**

No, n8n is not built on LangChain framework. However:
- n8n can **integrate** with LangChain for AI workflows
- They serve different purposes:
  - **n8n**: Workflow automation platform
  - **LangChain**: Framework for building AI applications
- You can use LangChain nodes inside n8n workflows

### Cost Effectiveness

**Pricing Comparison**:

| Aspect | n8n Self-Hosted | n8n Cloud | Zapier | Make | Pabbly |
|--------|----------------|-----------|--------|------|--------|
| **Monthly Cost** | Free (VPS ~$5-15) | $20+ | $20+ | $9+ | $19+ |
| **Workflows** | Unlimited | Limited by plan | Limited | Limited | Limited |
| **Executions** | Unlimited | Limited | Limited | Limited | Limited |
| **Data Privacy** | Full control | n8n servers | Zapier servers | Make servers | Pabbly servers |
| **Customization** | Complete | Limited | Minimal | Moderate | Limited |

**Cost Breakdown**:
- **VPS Hosting**: ₹400-1200/month (~$5-15/month)
- **Domain**: ₹500/year (~$6/year) - Optional
- **Total**: ~₹5000-15000/year vs ~₹15000-50000/year for cloud services

### Flexibility and Integration

**Why n8n is More Flexible**:

1. **Custom Code**: Write JavaScript/Python in nodes
2. **HTTP Request**: Connect to any API
3. **Function Nodes**: Complex data transformations
4. **Self-Hosting**: No platform restrictions
5. **Webhook Support**: Build custom integrations

### Comparison with Competitors

#### vs Zapier
- ✅ **n8n**: Free self-hosting, unlimited workflows
- ❌ **Zapier**: Expensive, limited on free plan
- ✅ **n8n**: More technical flexibility
- ❌ **Zapier**: Easier for complete beginners

#### vs Make (formerly Integromat)
- ✅ **n8n**: Better for complex workflows
- ✅ **Make**: Better visual scenario builder
- ✅ **n8n**: Self-hosting option
- ❌ **Make**: Cloud-only

#### vs Pabbly Connect
- ✅ **n8n**: More integrations
- ✅ **Pabbly**: One-time payment option
- ✅ **n8n**: Better documentation
- ❌ **Pabbly**: Simpler for basic tasks

**Quick Decision Guide**:
- Choose **n8n** if: You want control, privacy, and cost savings
- Choose **Zapier** if: You need simplicity and support
- Choose **Make** if: You want visual scenario planning
- Choose **Pabbly** if: You prefer one-time payments

---

## 5. n8n Hosting Options

### Local Host Setup

**Running on Your Laptop/Desktop**

**Pros**:
- ✅ Completely free
- ✅ No internet required for development
- ✅ Full control
- ✅ Quick testing environment
- ✅ Learn without commitment

**Cons**:
- ❌ Only works when computer is on
- ❌ Not accessible from outside your network
- ❌ No 24/7 automation
- ❌ Manual updates required

**Best For**:
- Learning n8n
- Testing workflows
- Development environment
- Personal projects

### Self-Hosted Cloud (VPS)

**Running on a Cloud Server**

**Pros**:
- ✅ 24/7 availability
- ✅ Accessible from anywhere
- ✅ Cost-effective (₹400-1200/month)
- ✅ Full control over data
- ✅ Can handle production workloads

**Cons**:
- ❌ Requires server management skills
- ❌ You handle updates and maintenance
- ❌ Need to configure security
- ❌ Technical setup required

**Best For**:
- Small to medium businesses
- Developers
- Privacy-conscious users
- Cost-conscious teams

### Production Cloud (n8n.io)

**Official n8n Hosting**

**Pros**:
- ✅ Fully managed service
- ✅ Automatic updates
- ✅ Professional support
- ✅ No maintenance required
- ✅ Built-in scaling

**Cons**:
- ❌ More expensive (starts at $20/month)
- ❌ Less control over infrastructure
- ❌ Data stored on n8n servers
- ❌ Plan limitations

**Best For**:
- Enterprises
- Teams wanting managed service
- Those who value support
- Rapid deployment needs

### Hosting Comparison Table

| Feature | Local Host | Self-Hosted VPS | n8n Cloud |
|---------|-----------|-----------------|-----------|
| **Cost** | Free | ~$5-15/month | $20+/month |
| **Setup Time** | 10 minutes | 1-2 hours | 5 minutes |
| **Availability** | When PC is on | 24/7 | 24/7 |
| **Maintenance** | Manual | You manage | Managed |
| **Public Access** | No | Yes | Yes |
| **Data Control** | Complete | Complete | Limited |
| **Support** | Community | Community | Official |
| **Scalability** | Limited | Manual | Automatic |

---

## 6. Local Setup Guide (Step-by-Step)

### Prerequisites

Before installing n8n locally, ensure you have:
- A computer (Windows, Mac, or Linux)
- Internet connection
- Administrator/sudo access
- Basic command line familiarity

### Installation Steps

#### Step 1: Visit n8n Documentation

Open your browser and go to:
```
https://docs.n8n.io/hosting/installation/
```

This is the official documentation and will have the most up-to-date instructions.

#### Step 2: Install Node.js

n8n requires Node.js version 18 or higher.

**For Windows**:
1. Go to https://nodejs.org/
2. Download the LTS (Long Term Support) version
3. Run the installer
4. Follow installation wizard
5. Restart your computer

**For Mac**:
```bash
# Using Homebrew
brew install node
```

**For Linux (Ubuntu/Debian)**:
```bash
# Using NodeSource
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt-get install -y nodejs
```

#### Step 3: Verify Node.js Installation

Open your terminal/command prompt and run:

```bash
node --version
```

You should see output like:
```
v18.17.0
```

**If you see an error**:
- Windows: Try restarting your computer
- Mac/Linux: Check if Node.js is in your PATH

#### Step 4: Verify NPM Installation

NPM (Node Package Manager) comes with Node.js. Verify it:

```bash
npm --version
```

Expected output:
```
9.8.1
```

**Understanding NPM**:
- NPM is like an app store for JavaScript packages
- It helps install and manage software libraries
- Comes bundled with Node.js automatically

#### Step 5: Install n8n Globally (Recommended)

Run this command in your terminal:

```bash
npm install n8n -g
```

**What this does**:
- `-g` flag installs globally (available everywhere)
- Downloads n8n from npm registry
- Takes 1-3 minutes depending on internet speed

**Alternative (NOT Recommended)**:
```bash
npx n8n
```
This runs n8n without installing, but:
- Downloads every time you run it
- Slower startup
- Temporary installation

**Why global installation is better**:
- Faster startup
- Permanent installation
- Available from any directory

#### Step 6: Start n8n

After installation, start n8n with:

```bash
n8n start
```

**What you'll see**:
```
Initializing n8n process
n8n ready on http://localhost:5678
Version: 1.x.x
```

**First-time startup**:
- Takes 20-30 seconds
- Creates default configuration
- Sets up database (SQLite)
- Generates encryption key

#### Step 7: Access n8n Interface

Open your web browser and go to:
```
http://localhost:5678
```

**First-Time Setup**:
1. Create owner account (email + password)
2. Set up your profile
3. Optionally enable telemetry
4. You'll see the n8n dashboard

**Understanding localhost:5678**:
- `localhost` = your own computer
- `5678` = port number (n8n's default)
- Only accessible from your computer

#### Step 8: Configure for Production (Optional)

If you want to access n8n from other devices:

```bash
# Set environment variables
export N8N_HOST=0.0.0.0
export N8N_PORT=5678
export N8N_PROTOCOL=http

# Start n8n
n8n start
```

Now accessible at: `http://YOUR_IP:5678`

### Troubleshooting

#### Issue: "command not found: n8n"

**Solution**:
1. Check if installation completed successfully
2. Try closing and reopening terminal
3. Reinstall with `npm install n8n -g`

#### Issue: "Port 5678 is already in use"

**Solution**:
```bash
# Use a different port
export N8N_PORT=5679
n8n start
```

#### Issue: Node version too old

**Solution**:
1. Uninstall old Node.js
2. Install latest LTS version
3. Verify with `node --version`

#### Issue: Permission denied

**Solution**:
```bash
# On Mac/Linux, use sudo
sudo npm install n8n -g

# Or fix npm permissions
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
export PATH=~/.npm-global/bin:$PATH
```

---

## 7. Self-Hosting with Hostinger (KVM VPS)

### Choosing the Right Plan

**Recommended: Hostinger KVM 2**

**Specifications**:
- **CPU**: 2 cores
- **RAM**: 8 GB
- **Storage**: 100 GB NVMe SSD
- **Bandwidth**: 8 TB/month
- **Price**: ~₹800-1200/month (~$10-15/month)

**Why KVM VPS?**
- **KVM (Kernel-based Virtual Machine)**: Full virtualization
- Better performance than shared hosting
- Dedicated resources
- Root access for complete control
- Can install any software

**When to Upgrade**:
- **KVM 1** (2GB RAM): Only for testing
- **KVM 2** (8GB RAM): Good for 10-50 workflows ✅
- **KVM 3+** (16GB+ RAM): Heavy automation (100+ workflows)

### VPS Setup Steps

#### Step 1: Purchase VPS from Hostinger

1. Go to [Hostinger.com](https://hostinger.com)
2. Navigate to VPS hosting
3. Select **KVM 2** plan
4. Choose payment cycle (annual for discount)
5. Complete purchase

#### Step 2: Access VPS Control Panel

After purchase:
1. Check your email for login credentials
2. Go to Hostinger control panel
3. Note down:
   - IP address
   - Root password
   - SSH port (usually 22)

#### Step 3: Connect via SSH

**For Windows (using PuTTY)**:
1. Download PuTTY from https://putty.org/
2. Enter your VPS IP address
3. Port: 22
4. Click Open
5. Login as: `root`
6. Enter password

**For Mac/Linux**:
```bash
ssh root@YOUR_VPS_IP
# Enter password when prompted
```

#### Step 4: Update System

Once connected, run:
```bash
# Update package list
apt update

# Upgrade all packages
apt upgrade -y

# Install essential tools
apt install -y curl wget git
```

### n8n Installation on VPS

#### Step 1: Install Node.js on VPS

```bash
# Download Node.js 18 setup script
curl -fsSL https://deb.nodesource.com/setup_18.x | bash -

# Install Node.js
apt install -y nodejs

# Verify installation
node --version
npm --version
```

#### Step 2: Install n8n

```bash
# Install n8n globally
npm install n8n -g

# Verify installation
n8n --version
```

#### Step 3: Create n8n Service (Run 24/7)

Create a systemd service file:

```bash
# Create service file
nano /etc/systemd/system/n8n.service
```

Paste this configuration:
```ini
[Unit]
Description=n8n - Workflow Automation Tool
After=network.target

[Service]
Type=simple
User=root
Environment="N8N_PORT=5678"
Environment="N8N_PROTOCOL=http"
Environment="N8N_HOST=0.0.0.0"
ExecStart=/usr/bin/n8n start
Restart=always
RestartSec=10

[Install]
WantedBy=multi-user.target
```

Save and exit (Ctrl+X, Y, Enter)

#### Step 4: Start n8n Service

```bash
# Reload systemd
systemctl daemon-reload

# Start n8n
systemctl start n8n

# Enable auto-start on boot
systemctl enable n8n

# Check status
systemctl status n8n
```

#### Step 5: Configure Firewall

```bash
# Allow n8n port
ufw allow 5678/tcp

# Allow SSH (important!)
ufw allow 22/tcp

# Enable firewall
ufw enable
```

#### Step 6: Access n8n

Open browser and visit:
```
http://YOUR_VPS_IP:5678
```

You should see the n8n setup screen!

#### Step 7: Secure Your Installation (Recommended)

**Set Basic Authentication**:

Edit service file:
```bash
nano /etc/systemd/system/n8n.service
```

Add these environment variables:
```ini
Environment="N8N_BASIC_AUTH_ACTIVE=true"
Environment="N8N_BASIC_AUTH_USER=your_username"
Environment="N8N_BASIC_AUTH_PASSWORD=your_secure_password"
```

Restart service:
```bash
systemctl daemon-reload
systemctl restart n8n
```

**Optional: Setup SSL/HTTPS** (if you have a domain):
1. Install Nginx
2. Install Certbot (Let's Encrypt)
3. Configure reverse proxy
4. Get SSL certificate

---

## 8. n8n Workspace Overview

### Dashboard Metrics

When you first log in, you'll see key metrics:

#### 1. Production Executions
- **What it shows**: Total workflow runs in production
- **Why it matters**: Tracks automation activity
- **Example**: 1,234 executions = your workflows ran 1,234 times

#### 2. Failed Executions
- **What it shows**: Number of workflows that encountered errors
- **Why it matters**: Helps identify problems
- **What to do**: Click to see error details and fix issues

#### 3. Failure Rate
- **What it shows**: Percentage of executions that failed
- **Good target**: Below 5%
- **Example**: 50 failures / 1000 executions = 5% failure rate

#### 4. Time Saved
- **What it shows**: Estimated time automation saved you
- **How calculated**: Based on workflow complexity
- **Example**: 240 hours saved = 30 workdays

#### 5. Runtime (Average)
- **What it shows**: Average execution time per workflow
- **Why it matters**: Helps optimize slow workflows
- **Example**: 2.5 seconds average runtime

### Templates

**Pre-built Workflow Library**

Access via: Dashboard → Templates

**Categories**:
- Marketing automation
- Data synchronization
- Social media management
- CRM integrations
- E-commerce workflows
- DevOps automation

**How to use**:
1. Browse templates
2. Click "Use this workflow"
3. Customize for your needs
4. Activate

**Popular Templates**:
- Gmail to Google Sheets logger
- Slack notifications for form submissions
- Automated backup workflows
- Social media posting scheduler

### Insights

**Analytics Dashboard**

Shows detailed metrics:
- Execution trends over time
- Most active workflows
- Error patterns
- Performance statistics

**Use cases**:
- Identify bottlenecks
- Monitor automation health
- Plan capacity upgrades
- Generate reports for stakeholders

---

## 9. Workflow Creation

### Adding Nodes

**What are Nodes?**
- Building blocks of workflows
- Each node performs one specific action
- Connected together to create automation

**How to Add Nodes**:

**Method 1: Click the + Button**
1. Open workflow editor
2. Click the **+** button on canvas
3. Search for node (e.g., "Gmail")
4. Click to add

**Method 2: Keyboard Shortcut**
- Press **N** key
- Search opens automatically
- Type and select node

**Method 3: Drag from Existing Node**
1. Click on a node
2. Click the **+** on the connection point
3. Select next node

**Node Categories**:
- **Trigger Nodes**: Start workflows (webhook, schedule, email)
- **Action Nodes**: Perform tasks (send email, update database)
- **Logic Nodes**: Control flow (IF, Switch, Merge)
- **Transform Nodes**: Manipulate data (Set, Function, Code)

### Using Sticky Notes

**Why Use Sticky Notes?**

Sticky notes are **essential for good workflow documentation**.

**Benefits**:
- Document complex logic
- Add context for future you
- Help team members understand
- Mark sections of workflow
- Add warnings or notes

**How to Add Sticky Notes**:
1. Right-click on canvas
2. Select "Add Sticky Note"
3. Type your documentation
4. Drag to position
5. Resize as needed

**Best Practices**:
```
✅ "This section handles payment processing"
✅ "TODO: Add error notification to admin"
✅ "⚠️ API rate limit: max 100 calls/minute"

❌ "Node"
❌ "abc"
```

**Color Coding**:
- Yellow: General notes
- Red: Warnings/Critical sections
- Green: Completed features
- Blue: Todo items

### Node Properties

**Accessing Node Properties**:
- Click on any node
- Right panel shows properties
- Configure settings here

**Common Properties**:

#### Execute Node
- **Test**: Run just this node
- **Execute**: Run from this node forward
- **Execute Previous**: Run previous nodes first

#### Node Actions
- **Duplicate**: Copy node with settings
- **Delete**: Remove node
- **Deactivate**: Disable without deleting
- **Rename**: Give descriptive name

#### Node Settings
- **Parameters**: Main configuration
- **Settings**: Advanced options
- **Notes**: Internal documentation

**Workflow Variables**:

Accessible in any node via expression:

```javascript
// Workflow ID
{{ $workflow.id }}

// Workflow name
{{ $workflow.name }}

// Current timestamp
{{ $now }}

// Previous node data
{{ $json }}
```

### Data Formats

**n8n Shows Data in Three Views**:

#### 1. Schema View
- Shows data structure
- Expandable tree format
- Best for exploring data
- Click to copy paths

#### 2. Table View
- Spreadsheet-like display
- Good for multiple items
- Easy comparison
- Can sort columns

#### 3. JSON View
- Raw JSON format
- Technical representation
- Copy-paste friendly
- Best for debugging

**Important**: All workflows in n8n are stored as JSON!

**Accessing Workflow JSON**:
1. Click workflow name → Download
2. Or: Settings → Workflow JSON
3. Can import/export for sharing

### Node Documentation

**Every Node Has Built-in Help**:

1. Click on any node
2. Click **?** icon (top right)
3. Opens node-specific documentation

**What You'll Find**:
- How the node works
- Parameter explanations
- Example configurations
- API limitations
- Common use cases

**Official Documentation**:
```
https://docs.n8n.io/integrations/builtin/
```

Browse all available nodes and their documentation.

---

## 10. Workflow Settings

Access via: Workflow → Settings (gear icon)

### Execution Logic (v0 vs v1)

**Understanding Versions**:

#### Version 0 (Legacy)
- Old execution model
- Sequential processing
- Can cause timing issues
- **NOT RECOMMENDED**

#### Version 1 (Current) ✅
- Modern execution model
- Better performance
- Improved error handling
- **RECOMMENDED FOR ALL NEW WORKFLOWS**

**Key Differences**:

| Feature | v0 | v1 |
|---------|----|----|
| **Speed** | Slower | Faster |
| **Error Handling** | Basic | Advanced |
| **Data Passing** | Limited | Flexible |
| **Future Support** | No | Yes |

**How to Change**:
1. Open workflow settings
2. Find "Execution Order"
3. Select **v1**
4. Save workflow

**Migration Note**:
- Existing v0 workflows work fine
- Change to v1 when you update them
- Test after migration

### Error Workflow

**What is Error Workflow?**

A special workflow that runs when another workflow fails.

**Why Use It?**:
- Get notified of failures immediately
- Log errors to database
- Send alerts to Slack/Email
- Automatic retry attempts
- Debug information capture

**How to Set Up**:

1. Create a new workflow for error handling
2. Add trigger: "Error Trigger"
3. Add notification nodes (email, Slack, etc.)
4. Save and activate

**In Your Main Workflow**:
1. Go to Settings
2. Select "Error Workflow"
3. Choose your error handling workflow
4. Save

**Example Error Workflow**:
```
Error Trigger
  ↓
Extract Error Details
  ↓
Send Slack Notification
  ↓
Log to Database
```

**Error Data Available**:
```javascript
{{ $json.error.message }}  // Error message
{{ $json.execution.id }}   // Failed execution ID
{{ $json.workflow.name }}  // Workflow that failed
{{ $json.node.name }}      // Node that failed
```

### Timezone Configuration

**CRITICAL: Set to Indian Timezone**

**Why This Matters**:
- Scheduled workflows use timezone
- Time-based triggers depend on it
- Data timestamps affected
- Report generation timing

**How to Set Timezone**:

**Method 1: Workflow Settings**
1. Open workflow
2. Go to Settings
3. Find "Timezone"
4. Select **Asia/Kolkata**
5. Save

**Method 2: Global Default**
```bash
# Set environment variable
export GENERIC_TIMEZONE=Asia/Kolkata

# Restart n8n
systemctl restart n8n
```

**Testing Timezone**:
1. Create schedule trigger
2. Set time to "09:00"
3. Verify it triggers at 9 AM IST

**Common Indian Timezones**:
- `Asia/Kolkata` - India Standard Time (IST) ✅
- `Asia/Calcutta` - Same as Kolkata

---

## 11. n8n Keyboard Shortcuts

### Essential Shortcuts

**Workflow Editor**:

| Shortcut | Action | Description |
|----------|--------|-------------|
| **N** | Open Nodes Panel | Quick node search |
| **Space** | Rename Node | Selected node |
| **Ctrl/Cmd + S** | Save Workflow | Save changes |
| **Ctrl/Cmd + Z** | Undo | Undo last action |
| **Ctrl/Cmd + Shift + Z** | Redo | Redo action |
| **Delete** | Delete Node | Remove selected node |
| **Ctrl/Cmd + C** | Copy Node | Copy selected node |
| **Ctrl/Cmd + V** | Paste Node | Paste copied node |
| **Ctrl/Cmd + D** | Duplicate Node | Duplicate selected |
| **F2** | Rename Node | Alternative rename |
| **Ctrl/Cmd + A** | Select All | Select all nodes |
| **Ctrl/Cmd + Enter** | Execute Workflow | Run entire workflow |
| **Ctrl/Cmd + Shift + Enter** | Execute Node | Run selected node |
| **Tab** | Next Input | Move to next field |
| **Shift + Tab** | Previous Input | Move to previous field |
| **Esc** | Close Panel | Close side panel |
| **?** | Keyboard Shortcuts | Show shortcuts help |

**Canvas Navigation**:

| Shortcut | Action |
|----------|--------|
| **Scroll** | Zoom in/out |
| **Ctrl/Cmd + Scroll** | Pan canvas |
| **Space + Drag** | Pan canvas |
| **Ctrl/Cmd + 0** | Zoom to fit |
| **Ctrl/Cmd + +** | Zoom in |
| **Ctrl/Cmd + -** | Zoom out |

**Node Connection**:

| Shortcut | Action |
|----------|--------|
| **Click + Drag** | Create connection |
| **Alt + Click** | Delete connection |
| **Shift + Click** | Multi-select nodes |

### Productivity Tips

**Speed Up Your Workflow**:

1. **Use N for Everything**
   - Don't use mouse to find nodes
   - Press N, type, Enter
   - Much faster

2. **Space for Quick Rename**
   - Select node
   - Press Space
   - Type new name
   - Enter

3. **Duplicate Instead of Recreate**
   - Ctrl/Cmd + D to duplicate
   - Modify copied node
   - Saves configuration time

4. **Use Sticky Notes Liberally**
   - Document as you build
   - Future you will thank present you

5. **Test Often**
   - Ctrl/Cmd + Shift + Enter
   - Test single nodes
   - Catch errors early

**Learn by Muscle Memory**:
- Week 1: Consciously use shortcuts
- Week 2: Shortcuts become natural
- Week 3: 2-3x faster workflow creation

---

## 12. Workflow Editor Features

### Editor Tab

**Main Building Interface**

**Components**:

1. **Canvas**
   - Drag and drop nodes
   - Connect workflows
   - Zoom and pan
   - Infinite workspace

2. **Node Panel** (Press N)
   - Search all nodes
   - Browse by category
   - Recent nodes
   - Favorites

3. **Properties Panel** (Right side)
   - Configure selected node
   - Set parameters
   - View documentation
   - Test node

4. **Top Toolbar**
   - Save workflow
   - Execute workflow
   - Workflow settings
   - Share workflow
   - Download JSON

**Canvas Tips**:
- Use grid for alignment
- Group related nodes
- Use colors for sections
- Add arrows with sticky notes

### Executions Tab

**Workflow Run History**

**What You See**:
- List of all executions
- Start time and duration
- Success/failure status
- Input and output data

**Execution Details**:
- Click any execution to see:
  - Each node's input/output
  - Execution time per node
  - Error messages (if failed)
  - Full execution path

**Filtering Options**:
- Status (success, error, waiting)
- Date range
- Workflow name
- Trigger type

**Use Cases**:
1. **Debugging**: See where workflow failed
2. **Auditing**: Track what was processed
3. **Performance**: Identify slow nodes
4. **Data Recovery**: Access past results

**Retention**:
- Default: Keep all executions
- Can configure in settings
- Database size consideration

### Evaluations Tab

**Testing and Debugging**

Based on the screenshot you provided, this tab shows:

**Purpose**:
- Test workflows before activating
- Debug issues in safe environment
- Validate data transformations
- Check API responses

**Features**:
- Run workflow with test data
- Step through execution
- Inspect intermediate results
- Modify and re-test

**Best Practices**:
1. Always test before activating
2. Use realistic test data
3. Test error scenarios
4. Verify all branches (IF conditions)
5. Check data formatting

**Testing Checklist**:
```
☐ Workflow executes without errors
☐ Data transforms correctly
☐ API calls return expected results
☐ Error handling works
☐ Timing is acceptable
☐ Notifications sent properly
```

---

## 13. Best Practices

### Workflow Organization

**Naming Conventions**:
```
✅ "Gmail to Sheets - Daily Contact Sync"
✅ "Stripe Payment → Send Receipt Email"
✅ "Social Media - Auto Post to Twitter & LinkedIn"

❌ "Workflow 1"
❌ "Test"
❌ "Untitled"
```

**Folder Structure** (if using self-hosted):
```
/workflows
  /marketing
    - email-automation.json
    - social-posting.json
  /sales
    - crm-sync.json
    - lead-notification.json
  /operations
    - data-backup.json
    - report-generation.json
```

### Error Handling

**Always Include**:
1. **Try-Catch Blocks**: Use IF nodes to handle errors
2. **Error Workflow**: Global error handler
3. **Notifications**: Alert on failures
4. **Retry Logic**: Auto-retry failed operations
5. **Logging**: Record errors for analysis

**Example Pattern**:
```
Main Process
  ↓
IF (Error Check)
  ├─ Success → Continue
  └─ Error → Send Alert + Retry
```

### Security

**Protect Credentials**:
- Never hardcode API keys in nodes
- Use n8n credential system
- Separate dev and production credentials
- Rotate keys regularly

**Data Privacy**:
- Be careful with PII (Personal Identifiable Information)
- Log minimal data
- Encrypt sensitive workflows
- Control access (user permissions)

### Performance

**Optimize Workflows**:
- Reduce API calls (cache where possible)
- Use bulk operations instead of loops
- Deactivate unused workflows
- Clean up old executions
- Monitor resource usage

**When to Split Workflows**:
- More than 20-30 nodes
- Multiple unrelated processes
- Performance degradation
- Hard to understand/maintain

### Documentation

**What to Document**:
1. **Purpose**: What does this workflow do?
2. **Trigger**: What starts it?
3. **Data Flow**: What data is processed?
4. **Dependencies**: What does it rely on?
5. **Maintenance**: How often to check?

**Use Sticky Notes For**:
- Section headers
- Complex logic explanations
- API limitations
- TODO items
- Version history

---

## 14. Common Use Cases

### For Individuals

1. **Email Management**
   - Auto-label emails
   - Save attachments to cloud
   - Forward important emails
   - Create tasks from emails

2. **Social Media**
   - Cross-post content
   - Schedule posts
   - Monitor mentions
   - Analytics collection

3. **Personal Finance**
   - Expense tracking
   - Bill reminders
   - Investment monitoring
   - Receipt organization

### For Small Businesses

1. **Customer Management**
   - CRM data sync
   - Lead notifications
   - Follow-up automation
   - Customer onboarding

2. **Marketing**
   - Email campaigns
   - Lead scoring
   - Social media management
   - Analytics reporting

3. **Operations**
   - Invoice generation
   - Inventory alerts
   - Order processing
   - Data backup

### For Developers

1. **DevOps**
   - CI/CD pipelines
   - Server monitoring
   - Deployment automation
   - Log aggregation

2. **Data Engineering**
   - ETL processes
   - Data validation
   - API integration
   - Database synchronization

3. **Testing**
   - Automated testing
   - Performance monitoring
   - Error reporting
   - Documentation generation

---

## 15. Resources and Links

### Official Resources

**Documentation**:
- Main Docs: https://docs.n8n.io/
- Node Reference: https://docs.n8n.io/integrations/builtin/
- API Docs: https://docs.n8n.io/api/

**Community**:
- Forum: https://community.n8n.io/
- Discord: https://discord.gg/n8n
- GitHub: https://github.com/n8n-io/n8n
- YouTube: https://www.youtube.com/c/n8n-io

### Learning Resources

**Tutorials**:
- Getting Started: https://docs.n8n.io/try-it-out/
- Video Tutorials: https://www.youtube.com/c/n8n-io
- Blog: https://blog.n8n.io/

**Courses**:
- n8n Academy (Official)
- YouTube community tutorials
- Udemy courses on automation

### Tools and Extensions

**Helpful Tools**:
- JSONata Exerciser: https://try.jsonata.org/
- Cron Expression Generator: https://crontab.guru/
- Regex Tester: https://regex101.com/
- API Testing: Postman, Insomnia

### Hosting Providers

**VPS Hosting** (for self-hosting):
- Hostinger: https://hostinger.com
- DigitalOcean: https://digitalocean.com
- Linode: https://linode.com
- Vultr: https://vultr.com
- Hetzner: https://hetzner.com

**Managed n8n Hosting**:
- n8n Cloud: https://n8n.io/cloud/

### Indian Community

**Local Resources**:
- Join Indian n8n community on Discord
- Search "n8n India" on LinkedIn
- WhatsApp groups (ask in forum)
- Local meetups (check Meetup.com)

---

## 📌 Quick Reference Card

### Installation One-Liner
```bash
npm install n8n -g && n8n start
```

### Essential Commands
```bash
n8n start                    # Start n8n
n8n update                   # Update n8n
n8n export:workflow --all    # Export all workflows
n8n import:workflow --input=file.json  # Import workflow
```

### Critical Settings
```bash
# Environment Variables
export GENERIC_TIMEZONE=Asia/Kolkata
export N8N_PORT=5678
export N8N_HOST=0.0.0.0
export N8N_PROTOCOL=http
```

### Must-Know Shortcuts
- **N** - Add node
- **Space** - Rename
- **Ctrl+S** - Save
- **Ctrl+Enter** - Execute

### Support Links
- Docs: docs.n8n.io
- Forum: community.n8n.io
- Discord: discord.gg/n8n

---

## 🎯 Next Steps

After reading this guide:

1. ✅ **Install n8n locally** (Section 6)
2. ✅ **Create your first workflow** (Section 9)
3. ✅ **Try a template** (Section 8)
4. ✅ **Join the community** (Section 15)
5. ✅ **Build a real automation** (Section 14)

---

## 📝 Changelog

**Version 1.0** (Current)
- Initial comprehensive guide
- Covers n8n basics to advanced
- Indian context and pricing
- Hostinger VPS setup guide
- Workspace overview
- Keyboard shortcuts
- Best practices

---

## 🙏 Contributing

Found an error or want to add something?

1. Create an issue on GitHub
2. Submit a pull request
3. Join community discussions
4. Share your use cases

---

## 📄 License

This documentation is free to use, share, and modify.  
Created with ❤️ for the Indian n8n community.

---

**Last Updated**: March 2026  
**n8n Version**: 1.x (Latest)  
**Author**: Claude AI  
**For**: Indian Automation Enthusiasts

---

## 🎓 Remember

> "The best time to automate was yesterday.  
> The second best time is now."

Start small, think big, automate everything! 🚀

