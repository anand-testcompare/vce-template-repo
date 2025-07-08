# Claude Code - Palantir MCP Setup Prompt

Copy and paste this entire prompt into Claude Code to set up Palantir MCP:

---

I need to set up Palantir MCP (Model Context Protocol) for Claude Code. I'll provide my configuration details, and you'll help me run the installation command.

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

1. **First, verify I've provided both required values** (enrollment URL and folder RID)

2. **Generate the complete `claude mcp add` command** using this exact pattern:
```bash
claude mcp add palantir-mcp \
  -e FOUNDRY_TOKEN="${FOUNDRY_TOKEN}" \
  -e NPM_CONFIG_REGISTRY="https://[MY-ENROLLMENT].palantirfoundry.com/artifacts/api/repositories/ri.artifacts.repository.discovered.foundry-mcp/contents/release/npm/" \
  -- npx "-y" "@palantir/mcp@latest" \
  "--foundry-api-url" "https://[MY-ENROLLMENT].palantirfoundry.com" \
  "--default-foundry-folder" "[MY-FOLDER-RID]"
```

3. **Execute the command** to install the MCP server

4. **Verify the installation** by running:
```bash
claude mcp list
```

5. **Test the connection** by asking me to:
   - Restart Claude Code to ensure MCP is loaded
   - Try a simple Foundry query like listing datasets in my default folder

## Example Values (for reference only)
Here's what the command looks like with example values:
- Enrollment: `compass-prod-us-east-1`
- Folder RID: `ri.compass.main-realm.folder.a1b2c3d4-e5f6-7890-abcd-ef1234567890`

Would produce:
```bash
claude mcp add palantir-mcp \
  -e FOUNDRY_TOKEN="${FOUNDRY_TOKEN}" \
  -e NPM_CONFIG_REGISTRY="https://compass-prod-us-east-1.palantirfoundry.com/artifacts/api/repositories/ri.artifacts.repository.discovered.foundry-mcp/contents/release/npm/" \
  -- npx "-y" "@palantir/mcp@latest" \
  "--foundry-api-url" "https://compass-prod-us-east-1.palantirfoundry.com" \
  "--default-foundry-folder" "ri.compass.main-realm.folder.a1b2c3d4-e5f6-7890-abcd-ef1234567890"
```

## Troubleshooting Notes
If the installation fails, check:
1. Is FOUNDRY_TOKEN properly set? Test with: `echo $FOUNDRY_TOKEN | head -c 10`
2. Can NPM access the registry? Test with: `npm view @palantir/mcp@latest`
3. Are the enrollment URL and folder RID correct?

Please proceed with the installation!