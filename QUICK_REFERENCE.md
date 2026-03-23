# 🚀 n8n Quick Reference Sheet

## Installation

### Local Setup
```bash
# Install globally
npm install n8n -g

# Start n8n
n8n start

# Access at
http://localhost:5678
```

### VPS Setup (Hostinger)
```bash
# Install Node.js
curl -fsSL https://deb.nodesource.com/setup_18.x | bash -
apt install -y nodejs

# Install n8n
npm install n8n -g

# Create systemd service
nano /etc/systemd/system/n8n.service

# Start service
systemctl start n8n
systemctl enable n8n
```

## Essential Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| **N** | Open nodes panel |
| **Space** | Rename selected node |
| **Ctrl+S** | Save workflow |
| **Ctrl+Enter** | Execute workflow |
| **Ctrl+Shift+Enter** | Execute selected node |
| **Delete** | Delete node |
| **Ctrl+D** | Duplicate node |
| **Ctrl+Z** | Undo |
| **?** | Show shortcuts |

## Node Categories

- **Trigger**: Webhook, Schedule, Email Trigger
- **Action**: HTTP Request, Gmail, Slack
- **Logic**: IF, Switch, Merge
- **Transform**: Set, Function, Code

## Data Access

```javascript
// Current node data
{{ $json }}

// Workflow info
{{ $workflow.name }}
{{ $workflow.id }}

// Timestamp
{{ $now }}

// Previous node
{{ $node["Node Name"].json }}
```

## Critical Settings

### Timezone (MUST SET)
```
Asia/Kolkata (IST)
```

### Execution Version
```
✅ Use Version 1 (v1)
❌ Avoid Version 0 (v0)
```

## Common Use Cases

### Email to Sheet
```
Email Trigger → Extract Data → Google Sheets
```

### Form to CRM
```
Webhook → Transform → CRM Create
```

### Daily Report
```
Schedule → Database Query → Send Email
```

## Environment Variables

```bash
# Timezone
export GENERIC_TIMEZONE=Asia/Kolkata

# Port
export N8N_PORT=5678

# Host
export N8N_HOST=0.0.0.0

# Protocol
export N8N_PROTOCOL=http
```

## Hosting Costs (Indian Context)

| Option | Monthly Cost |
|--------|--------------|
| Local | Free |
| VPS (Hostinger) | ₹800-1200 |
| n8n Cloud | ₹1600+ |
| Zapier Equivalent | ₹1600-4000 |

## Support Links

- **Docs**: https://docs.n8n.io/
- **Community**: https://community.n8n.io/
- **Discord**: https://discord.gg/n8n
- **GitHub**: https://github.com/n8n-io/n8n

## Best Practices

1. ✅ Always use sticky notes for documentation
2. ✅ Set timezone to Asia/Kolkata
3. ✅ Use execution version v1
4. ✅ Create error workflows
5. ✅ Test before activating
6. ✅ Use descriptive names
7. ✅ Regular backups

## Troubleshooting

### n8n won't start
```bash
# Check if port is in use
lsof -i :5678

# Use different port
export N8N_PORT=5679
n8n start
```

### Node version error
```bash
# Check version
node --version

# Should be 18+
```

### Permission denied
```bash
# Use sudo for global install
sudo npm install n8n -g
```

## Quick Commands

```bash
# Export all workflows
n8n export:workflow --all

# Import workflow
n8n export:workflow --all --output=backup.json

# Update n8n
npm update n8n -g

# Check version
n8n --version
```

---

**Remember**: Start simple, test often, document everything!
