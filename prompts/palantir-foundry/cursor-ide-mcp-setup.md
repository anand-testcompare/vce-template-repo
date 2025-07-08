# Cursor IDE - Palantir MCP Setup Prompt

Copy and paste this entire prompt into Cursor's AI chat to set up Palantir MCP:

---

I need help setting up Palantir MCP (Model Context Protocol) for Cursor IDE. I'll provide my configuration details, and you'll help me update my Cursor settings file.

## Prerequisites Confirmation
I have already completed these prerequisites:
- ✅ My FOUNDRY_TOKEN environment variable is set in my shell profile
- ✅ NPM authentication is configured for my Palantir instance
- ✅ Control Panel permissions are enabled in my Foundry instance

## My Configuration Details

**Please ask me for the following information if not provided:**
1. **My Foundry Enrollment URL** (example format: `compass-prod-us-east-1`)
2. **My Default Compass Folder RID** (example format: `ri.compass.main-realm.folder.12345678-abcd-1234-5678-abcdef123456`)

**My Details:**
- Enrollment URL: [PASTE YOUR ENROLLMENT HERE]
- Compass Folder RID: [PASTE YOUR FOLDER RID HERE]

## What I Need You To Do

1. **First, check if my settings file exists** at `~/.cursor/settings.json`
   - If it exists, read the current contents
   - If not, we'll create a new one

2. **Create or update the settings file** with the MCP configuration following this exact pattern:
```json
{
  "mcpServers": {
    "palantir": {
      "command": "npx",
      "args": [
        "-y",
        "@palantir/mcp@latest",
        "--foundry-api-url",
        "https://[MY-ENROLLMENT].palantirfoundry.com",
        "--default-foundry-folder",
        "[MY-FOLDER-RID]"
      ],
      "env": {
        "NPM_CONFIG_REGISTRY": "https://[MY-ENROLLMENT].palantirfoundry.com/artifacts/api/repositories/ri.artifacts.repository.discovered.foundry-mcp/contents/release/npm/",
        "FOUNDRY_TOKEN": "${FOUNDRY_TOKEN}"
      }
    }
  }
}
```

3. **If the file already exists**, merge the MCP configuration properly:
   - Preserve all existing settings
   - Add or update only the `mcpServers.palantir` section
   - Ensure valid JSON syntax

4. **Write the updated configuration** to `~/.cursor/settings.json`

5. **Provide clear next steps**:
   - Remind me to completely restart Cursor IDE
   - Explain how to verify MCP is loaded (check the MCP indicator in Cursor)
   - Suggest a test query to confirm Foundry connection

## Example Values (for reference only)
Here's what a completed configuration looks like:
- Enrollment: `compass-prod-us-east-1`
- Folder RID: `ri.compass.main-realm.folder.a1b2c3d4-e5f6-7890-abcd-ef1234567890`

Results in:
```json
{
  "mcpServers": {
    "palantir": {
      "command": "npx",
      "args": [
        "-y",
        "@palantir/mcp@latest",
        "--foundry-api-url",
        "https://compass-prod-us-east-1.palantirfoundry.com",
        "--default-foundry-folder",
        "ri.compass.main-realm.folder.a1b2c3d4-e5f6-7890-abcd-ef1234567890"
      ],
      "env": {
        "NPM_CONFIG_REGISTRY": "https://compass-prod-us-east-1.palantirfoundry.com/artifacts/api/repositories/ri.artifacts.repository.discovered.foundry-mcp/contents/release/npm/",
        "FOUNDRY_TOKEN": "${FOUNDRY_TOKEN}"
      }
    }
  }
}
```

## Important Notes
- The settings file must be valid JSON
- The `FOUNDRY_TOKEN` uses `${FOUNDRY_TOKEN}` syntax to read from environment
- Cursor must be fully restarted (not just reloaded) for MCP changes to take effect

Please proceed with the setup!