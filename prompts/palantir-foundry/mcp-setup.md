# Palantir MCP Self-Configuration Prompts

These prompts help configure Palantir MCP for various AI development tools. Each prompt is designed to be self-sufficient - just copy the entire contents of the appropriate file and paste it into your AI tool.

## Available Setup Guides

### 🤖 Claude Code
- **File**: [`claude-code-mcp-setup.md`](./claude-code-mcp-setup.md)
- **Usage**: Copy the entire file contents and paste into Claude Code
- **Method**: Uses `claude mcp add` command

### 💎 Gemini CLI
- **File**: [`gemini-cli-mcp-setup.md`](./gemini-cli-mcp-setup.md)
- **Usage**: Copy the entire file contents and paste into Gemini CLI
- **Method**: Updates `~/.gemini/settings.json`

### 📝 Cursor IDE
- **File**: [`cursor-ide-mcp-setup.md`](./cursor-ide-mcp-setup.md)
- **Usage**: Copy the entire file contents and paste into Cursor's AI chat
- **Method**: Updates `~/.cursor/settings.json`

## Prerequisites (Required for All Tools)

Before using any of these setup prompts, ensure you have:

1. **FOUNDRY_TOKEN Environment Variable**
   ```bash
   export FOUNDRY_TOKEN="your-token-here"
   ```
   Add this to your shell profile (`~/.bashrc`, `~/.zshrc`, etc.)

2. **NPM Authentication**
   Configure NPM to authenticate with your Palantir instance

3. **Control Panel Permissions**
   Enable appropriate permissions in your Foundry Control Panel

## Information You'll Need

Each setup prompt will ask for:
- **Enrollment URL**: Your Foundry instance (e.g., `compass-prod-us-east-1`)
- **Compass Folder RID**: Your default working folder (e.g., `ri.compass.main-realm.folder.12345678-abcd-1234-5678-abcdef123456`)

## Quick Start

1. Choose your AI tool from the list above
2. Open the corresponding setup file
3. Copy the **entire contents** of the file
4. Paste into your AI tool
5. Follow the prompts to complete setup

## Integration Best Practices

```markdown
# Foundry Integration Best Practices

You are an expert in Palantir Foundry workflows and MCP integration. Help me establish best practices for using AI tools with Foundry data.

**My Setup:**
- Foundry Enrollment: [USER_FILLS_IN]
- Primary Compass Projects: [USER_LISTS_PROJECTS]
- Common Use Cases: [USER_DESCRIBES_WORKFLOWS]

**Integration Guidance Needed:**

1. **Data Access Patterns**
   - Best practices for querying datasets through MCP
   - How to maintain data governance while using AI tools
   - Recommended dataset size limits for AI analysis

2. **Code Generation Standards**
   - Foundry-specific coding conventions
   - Pipeline Builder integration patterns
   - AIP Logic best practices

3. **Security & Compliance**
   - Token management and rotation
   - Data privacy considerations
   - Audit trail maintenance

4. **Workflow Optimization**
   - When to use MCP vs direct Foundry access
   - AI-assisted development patterns
   - Testing and validation approaches

Please provide specific examples and templates for my use cases, focusing on practical implementation rather than theoretical concepts.
```

## Troubleshooting Guide

```markdown
# Palantir MCP Troubleshooting

You are helping me debug Palantir MCP connection issues. I'm experiencing problems with my MCP setup.

**My Configuration:**
- Platform: [Claude Code / Gemini CLI / Cursor]
- Enrollment: [USER_FILLS_IN]
- Error/Issue: [USER_DESCRIBES_PROBLEM]

**Diagnostic Information:**
```bash
# Environment check
echo $FOUNDRY_TOKEN
# Result: [USER_PASTES_OUTPUT]

# NPM auth check  
npm view @palantir/mcp@latest
# Result: [USER_PASTES_OUTPUT]

# MCP status check
[claude mcp list / /mcp / IDE status]
# Result: [USER_PASTES_OUTPUT]
```

**Common Issues to Check:**
1. Control Panel permissions enabled?
2. Environment variable properly set and sourced?
3. NPM authentication working?
4. Network/firewall restrictions?
5. Configuration file syntax correct?

Please help me systematically diagnose and resolve this issue with specific commands and solutions.
```
