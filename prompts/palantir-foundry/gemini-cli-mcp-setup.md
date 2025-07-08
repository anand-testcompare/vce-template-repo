# Gemini CLI - Palantir MCP Setup Prompt

Copy and paste this entire prompt into Gemini CLI to set up Palantir MCP:

---

I need help setting up Palantir MCP (Model Context Protocol) for Gemini CLI. I'll provide my configuration details, and you'll help me update my settings file.

## Prerequisites Confirmation
I have already completed these prerequisites:
- ✅ My FOUNDRY_TOKEN environment variable is set in my shell profile
- ✅ NPM authentication is configured for my Palantir instance
- ✅ Control Panel permissions are enabled in my Foundry instance

## My Configuration Details

**Please ask me for the following information:**
1. **My Foundry Enrollment URL** (example format: `compass-prod-us-east-1`)
2. **My Default Compass Folder RID** (example format: `ri.compass.main-realm.folder.12345678-abcd-1234-5678-abcdef123456`)

## Current Gemini Settings
My current `~/.gemini/settings.json` file contains:
```json
[If you have existing settings, paste them here. If the file doesn't exist yet, just say "empty" or "new file"]
```

## What I Need You To Do

1. **First, ask me for my enrollment URL and folder RID** if I haven't provided them above

2. **Create or update my settings file** at `~/.gemini/settings.json` with the MCP configuration

3. **The MCP configuration should follow this exact pattern:**
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

4. **If I have existing settings**, merge the MCP configuration without overwriting other configurations

5. **After updating the file**, tell me the exact steps to:
   - Save the file
   - Restart Gemini CLI (using `/quit` then `gemini`)
   - Verify the connection (using `/mcp` command)
   - Test with a simple Foundry query

## Example Values (for reference only)
Here's what a completed configuration looks like:
- Enrollment: `compass-prod-us-east-1`
- Folder RID: `ri.compass.main-realm.folder.a1b2c3d4-e5f6-7890-abcd-ef1234567890`

## Important Notes
- The `FOUNDRY_TOKEN` reference uses `${FOUNDRY_TOKEN}` to read from my environment variable
- The NPM registry URL must match my enrollment exactly
- The folder RID should be my default working folder in Compass

Please proceed with helping me set this up!