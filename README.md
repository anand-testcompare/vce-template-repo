# Vibe Coded Excellence (VCE)

_Because scrolling through command history and pressing enter is hard work_

## Quick Start

### Installing Claude Commands

```bash
# Copy specific prompts to use with your AI tool
cp prompts/development/git-workflows.md ~/.claude/commands/

# Or browse the prompts directory and pick what you need
ls -la prompts/
```

### Usage Examples

```bash
# Research a company for demo data
claude company-analysis "JNJ biologics"

# Auto-test a web application  
claude web-testing "http://localhost:3000"

# Debug GitHub Actions
claude github-actions-debug

# Create PR from current changes
claude git-workflows
```

## Prompt Categories

### 🔧 Development (`/prompts/development`)
- **git-workflows.md** - Automated git operations and PR creation
- **github-actions-debug.md** - Troubleshoot failing workflows
- **issue-grooming.md** - Automated issue management
- **media-downloader.md** - CLI tool creation
- **implement-highest-priority-issue.md** - Task prioritization

### 🏢 Palantir Foundry (`/prompts/palantir-foundry`)
- **mcp-setup.md** - Self-configuring MCP setup for:
  - Claude Code
  - Gemini CLI
  - Cursor IDE
  - Plus troubleshooting guide and best practices

### 🔍 Research (`/prompts/research`)
- **company-analysis.md** - Comprehensive company research methodology

### 🤖 Automation (`/prompts/automation`)
- **file-organization.md** - Intelligent file system organization
- **web-testing.md** - Playwright-based web app testing

### 🔒 Security (`/prompts/security`)
- **s3-exploration.md** - AWS S3 bucket analysis

## Using the Prompts

These prompts work with any capable AI assistant (Claude, Gemini, Cursor, etc.). Just:

1. Browse to the relevant category folder
2. Open the prompt file you need
3. Copy the prompt content
4. Paste into your AI tool
5. Fill in any `[USER_FILLS_IN]` placeholders
6. Let the AI guide you through the process

### Palantir MCP Setup Example

```bash
# Just copy the entire prompt for your tool and paste into your AI session
cat prompts/palantir-foundry/mcp-setup.md
# Find the section for your tool (Claude Code, Gemini, Cursor)
# Copy that prompt, paste into your AI, and it handles the rest
```

## What's This About?

AI coding is everywhere. Some people are freaking out, others are pretending it doesn't exist. I'm trying to make it not suck.

The real problem isn't that AI writes bad code - it's that AI makes it **really easy to scale bad habits**. You know what I'm talking about:

- That commit message that says "fix" with 47 changed files
- The React component that somehow needs 15 dependencies  
- The function that's 200 lines long because "it works"
- The database query that would make your DBA cry

We now have this opportunity to literally teach the robots our hard-learned lessons. Instead of everyone having to live through their own production disasters to learn best practices, we can just encode that wisdom upfront.

## Why I Built This

I got tired of typing detailed commit messages.

I'd finish some work, go to commit, and then face that moment of "ugh, I should write a proper commit message with context and reasoning..." vs "screw it, `git commit -m 'fixed stuff'`"

Too often, laziness won. Then six months later I'd be staring at git history like "WHAT DID PAST ME EVEN DO HERE??"

So I built a prompt that lets me type a couple tabs, walk away, come back to a perfectly formatted commit with proper context and clear rollback points. No more 1000-line commits with the message "updates."

That's when it clicked - what if all the shortcuts made the **good practice** easier than the bad practice?

## The Approach

This isn't about being the code police or building some enterprise framework. It's about:

- **Lazy optimization**: Making good practices the path of least resistance
- **Battle-tested shortcuts**: Prompts that encode lessons from production disasters
- **Anti-overthinking**: Simple solutions that actually work at scale
- **Practical examples**: Examples from actual projects, not theoretical BS
- **Quick setup**: For when you're flipping to new PCs, running from servers, etc.

## What's In Here

This is mostly shortcuts and little scripts that I ended up going back-and-forth with Claude or Gemini to get right. You know the drill - you start with some vague prompt, get 80% of what you want, then spend 20 minutes refining it until it actually works.

At the end of those sessions, I'd ask: "Hey, if you had just one shot to generate this perfectly, what would that prompt be?"

That's what these markdown files are. Think of it as micro reinforcement learning or prompt distillation - taking all that trial and error and boiling it down to the one-shot version that actually works.

**Note**: I've tried a handful of AI IDEs, but I'm 90% Claude CLI or Gemini right now, so those will be updated way more often. This is just my starting point when setting up new environments.

## Summary from my rant at chatgpt

I've found myself having a lot fewer opinions, but a lot stronger ones. e.g., I hated sonnet for a long time now I am happily slapping $200 on their desk every month. I used to fiend about every new release/feature from langchain/langgraph and now I have zero desire to add more black box crap ontop of black boxes and even if that code base is stable now (I doubt it), I'm not touching that shit for anything that isn't a just for fun type project.

## Contributing

Got a prompt that saves you time? Throw it in here.
If you're a jaded sr. dev and want to talk shit about what software dev will look like in a few years, hmu. I miss those discussions
Want to fork this and build something completely different? Go for it. No attribution needed.
Feel compelled to take over ownership, cool I'll transfer it (assuming you actually know what you're doing)
This is just me putting my thoughts somewhere public instead of keeping them in random text files in Obsidian. If it helps someone else avoid a production fire, cool. If not, at least I have a backup of my prompts now.

## License

This isn't the cursor/windsurf/lovable prompt leak fiasco... MIT license, do w/e.