# Vibe Coded Excellence (VCE) - Self-Configuration Prompts

## claude-code-mcp-setup.md

```markdown
# Claude Code MCP Self-Configuration Prompt

You are helping me configure Palantir MCP for Claude Code. I have already completed these prerequisites:
- Environment variable FOUNDRY_TOKEN is set
- NPM authentication is configured
- Control Panel permissions are enabled

Please help me run the correct `claude mcp add` command using these parameters:

**My Configuration:**
- Enrollment URL: [USER_FILLS_IN]
- Compass Folder RID: [USER_FILLS_IN]

**Expected Command Pattern:**
```bash
claude mcp add palantir-mcp \
  -e FOUNDRY_TOKEN="${FOUNDRY_TOKEN}" \
  -e NPM_CONFIG_REGISTRY="https://[ENROLLMENT].palantirfoundry.com/artifacts/api/repositories/ri.artifacts.repository.discovered.foundry-mcp/contents/release/npm/" \
  -- npx "-y" "@palantir/mcp@latest" \
  "--foundry-api-url" "https://[ENROLLMENT].palantirfoundry.com" \
  "--default-foundry-folder" "[COMPASS_RID]"
```

After generating the command:
1. Execute it for me
2. Run `claude mcp list` to verify installation
3. Suggest next steps for testing the integration

Replace the placeholders with my actual values and execute the installation.
```

## gemini-cli-mcp-setup.md

```markdown
# Gemini CLI MCP Self-Configuration Prompt

You are helping me configure Palantir MCP for Gemini CLI. I have already completed these prerequisites:
- Environment variable FOUNDRY_TOKEN is set  
- NPM authentication is configured
- Control Panel permissions are enabled

Please help me update my Gemini CLI settings file with the correct configuration.

**My Configuration:**
- Enrollment URL: [USER_FILLS_IN]
- Compass Folder RID: [USER_FILLS_IN]

**Settings File Location:** `~/.gemini/settings.json`

**Current Settings (if any):**
```json
[USER_PASTES_CURRENT_SETTINGS]
```

**Required MCP Configuration Pattern:**
```json
{
  "mcpServers": {
    "palantir": {
      "command": "npx",
      "args": [
        "-y",
        "@palantir/mcp@latest",
        "--foundry-api-url",
        "https://[ENROLLMENT].palantirfoundry.com",
        "--default-foundry-folder",
        "[COMPASS_RID]"
      ],
      "env": {
        "NPM_CONFIG_REGISTRY": "https://[ENROLLMENT].palantirfoundry.com/artifacts/api/repositories/ri.artifacts.repository.discovered.foundry-mcp/contents/release/npm/",
        "FOUNDRY_TOKEN": "${FOUNDRY_TOKEN}"
      }
    }
  }
}
```

Please:
1. Merge this MCP configuration with my existing settings
2. Provide the complete updated settings.json file
3. Remind me to restart Gemini CLI with `/quit` then `gemini`
4. Show me how to verify with `/mcp` command

Replace the placeholders with my actual values and provide the complete configuration.
```

## foundry-integration-patterns.md

```markdown
# Foundry Integration Patterns

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

## mcp-troubleshooting.md

```markdown
# MCP Troubleshooting Assistant

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
