---
theme: seriph
background: https://images.unsplash.com/photo-1451187580459-43490279c0fa?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80

addons:
  - slidev-addon-qrcode

class: text-center
highlighter: shiki
lineNumbers: true
info: |
  ## Agentic Coding with Antigravity CLI

  By Kenneth Kousen

  Learn more at [KouseniT](https://kousenit.com)
drawings:
  persist: false
transition: slide-left
title: "Agentic Coding with Antigravity CLI"
mdc: true
slidev:
  slide-number: true
  controls: true
  progress: true
css: unocss
---

<style>
.slidev-page-num {
  display: block !important;
  opacity: 1 !important;
  visibility: visible !important;
  position: fixed !important;
  bottom: 1rem !important;
  right: 1rem !important;
  z-index: 100 !important;
  color: #666 !important;
  font-size: 0.875rem !important;
}
</style>

# Agentic Coding with Antigravity CLI

## Google's AI Agent in Your Terminal

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

---

# Contact Info

Ken Kousen
Kousen IT, Inc.

- ken.kousen@kousenit.com
- http://www.kousenit.com
- http://kousenit.org (blog)
- Social Media:
  - [@kenkousen](https://twitter.com/kenkousen) (twitter)
  - [@kenkousen@foojay.social](https://foojay.social/@kenkousen) (mastodon)
  - [@kousenit.com](https://bsky.app/profile/kousenit.com) (bluesky)
- *Tales from the jar side* (free newsletter)
  - https://kenkousen.substack.com
  - https://youtube.com/@talesfromthejarside

---

# Course Overview

<v-clicks>

- **Duration**: 5 hours of hands-on learning
- **Format**: Instructor-led with multiple labs
- **Hands-on Labs**: Real codebases in Python, JavaScript, Java
- **Prerequisites**: Command-line experience, development background

</v-clicks>

---

# Topics Covered

<v-clicks>

- **Foundation**: Installation, CLI basics, authentication
- **Core Skills**: File operations, shell integration, context management
- **Customization**: AGENTS.md, custom commands, settings.json
- **Safety**: Sandbox mode, permission rules, checkpointing
- **Advanced**: MCP integration, skills/plugins, session management

</v-clicks>

---

# What's New in Antigravity CLI 1.0.x

<v-clicks>

- **Initial 1.0.0 release** of the Antigravity CLI — a Go-based terminal agent
- **Multi-model** sessions: Gemini, Claude, and GPT-OSS via `/model` (1.0.5)
- **`models` subcommand** + `--model` flag to pick a model at launch (1.0.5)
- **`/permissions`** command to manage tool permission rules in-CLI (1.0.5)
- **G1 credits** with `/credits`, `/usage`, `/quota` when quota runs out (1.0.3)
- **MCP via `url`** in `mcp_config.json`; parallel server init (1.0.5/1.0.6)
- **SQLite conversation format** + `/resume`, `--continue`, `--conversation` (1.0.4)
- **Plugin discovery** for skills and subagents (1.0.1)
- **Latest stable track**: Antigravity CLI `1.0.6`

</v-clicks>

---

# What is Antigravity CLI?

<v-clicks>

- Google's Go-based AI coding agent for the terminal (binary: `agy`)
- **Multi-model**: Gemini 3.x, Claude Sonnet/Opus 4.6, GPT-OSS — switch with `/model`
- Built-in tools: web search, file ops, shell, web fetch
- Model Context Protocol (MCP) support via `mcp_config.json`
- Shares config with the Antigravity 2.0 desktop app (`/export`)

</v-clicks>

---

# Key Differentiators

<v-clicks>

- **Model choice**: mix Gemini, Claude, and GPT-OSS in one tool
- **Google Search Grounding**: real-time web access
- **Free tier + G1 credits**: keep working when quota runs out
- **Desktop continuity**: shares conversations with Antigravity 2.0
- **MCP Native**: built-in Model Context Protocol support

</v-clicks>

---

# Models Available

<v-clicks>

- **Gemini 3.1 Pro**: high-capability Gemini model for complex coding
- **Gemini 3.5 Flash**: faster, lower-cost option (Low/Medium/High)
- **Claude Sonnet 4.6 / Opus 4.6**: Anthropic models (thinking)
- **GPT-OSS 120B**: open-weights option
- **List models**: `agy models`  ·  **Switch**: `/model` or `--model`

</v-clicks>

---

# Quota & Credits

<v-clicks>

- **Free tier**: sign in with a Google account to get started
- **G1 credits**: kick in automatically when standard quota runs out
- **In-CLI panels**: `/credits`, `/usage`, `/quota` for real-time status
- Manage models and preferences via `/settings`

</v-clicks>

📖 **Docs**: [antigravity.google/docs](https://antigravity.google/docs)

---

# Installation

<v-clicks>

- **macOS / Linux**: `curl -fsSL https://antigravity.google/cli/install.sh | bash`
- **Windows (PowerShell)**: `irm https://antigravity.google/cli/install.ps1 | iex`
- Installs the `agy` binary to `~/.local/bin/`
- Verify: `agy --version`  ·  Update later: `agy update`

</v-clicks>

```bash
# Install (macOS / Linux)
curl -fsSL https://antigravity.google/cli/install.sh | bash

# Verify installation
agy --version
```

---

# Authentication

<v-clicks>

- **Google Sign-In** (default): launches automatically on first run
- **Remote / SSH**: shows an authorization URL with a one-time code
- **API key (alternative)**: `export ANTIGRAVITY_API_KEY="your-key"`
- Credentials persist via OAuth in `~/.gemini/`

</v-clicks>

```bash
# First run: sign in with your Google account
agy

# Alternative: API key for scripts / headless use
export ANTIGRAVITY_API_KEY="your-api-key"
agy -p "Summarize this repo"
```

---

# Basic Usage Modes

<v-clicks>

- **Interactive REPL**: `agy` - Start a conversation
- **One-shot / print**: `agy -p "prompt"` - Single response
- **Piped input**: `echo "task" | agy -p`
- **Interactive with initial prompt**: `agy -i "initial context"`

</v-clicks>

```bash
# Interactive mode
agy

# One-shot (print) mode
agy -p "Explain what this codebase does"

# Start interactively with an initial prompt
agy -i "You are a Python expert"
```

---
layout: image-right
image: https://images.unsplash.com/photo-1555949963-ff9fe0c870eb?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80
backgroundSize: cover
---

# Core Features

<div class="text-center mt-20">
  <h2 class="text-4xl font-bold text-white bg-black bg-opacity-60 px-6 py-3 rounded-lg">
    Essential Capabilities
  </h2>
  <p class="text-xl text-white bg-black bg-opacity-60 px-4 py-2 rounded mt-4">
    Master the fundamentals
  </p>
</div>

---

# File References with @

<v-clicks>

- Reference files directly: `@./src/main.js`
- Reference directories: `@./src/` (recursive)
- Reference images: `@./screenshot.png`
- Multiple references in one prompt

</v-clicks>

```bash
# Reference a specific file
agy -p "Explain @./src/app.py"

# Reference multiple files
agy -p "Compare @./old.js and @./new.js"

# Reference a directory
agy -p "Analyze the architecture in @./src/"
```

---

# Shell Integration with !

<v-clicks>

- Execute shell commands: `!git status`
- Toggle persistent shell mode: `!`
- The agent can observe and analyze output
- Combine with AI analysis

</v-clicks>

```bash
# In interactive mode:
> !npm test
# The agent sees the test output

> !git diff
# Ask the agent to analyze the changes

# Toggle persistent shell mode
> !
```

---

# Slash Commands: Navigation

<v-clicks>

- `/help` - Show available commands and shortcuts
- `/context` - View loaded context and token usage
- `/model` - Switch the active model mid-session
- `/settings` - Open settings and preferences

</v-clicks>

---

# Slash Commands: Workflow

<v-clicks>

- `/agent <task>` - Dispatch an asynchronous subagent
- `/permissions` - Add/edit/remove tool permission rules
- `/usage` - Session, quota, and rate-limit status

</v-clicks>

---

# Slash Commands: Session Control

<v-clicks>

- `/resume` - Open the conversation browser
- `/export` - Send the session to the Antigravity 2.0 desktop app
- `/credits` · `/quota` - Credit balance and quota panels

</v-clicks>

---

# Slash Commands in Action (Context)

```bash
# Show what context is loaded and token usage
/context

# Switch the active model
/model

# Manage tool permission rules
/permissions

# Open settings and preferences
/settings
```

---

# Slash Commands in Action (Sessions)

```bash
# Open the conversation browser
/resume

# Dispatch an async subagent task
/agent refactor the auth module

# Push this session to the desktop app
/export
```

---

# Keyboard Shortcuts: Editing

<v-clicks>

- `Ctrl+L` - Clear screen
- `Ctrl+V` - Paste text/images
- `Ctrl+R` - Open the Artifact Review panel

</v-clicks>

---

# Keyboard Shortcuts: Control

<v-clicks>

- `Esc` - Interrupt the active agent stream
- `Ctrl+C` - Cancel current operation
- `Ctrl+D` `Ctrl+D` - Exit Antigravity CLI (press twice)

</v-clicks>

---

# Built-in Tools

<v-clicks>

- **File System**: `read_file()`, `write_file()`, `replace()`, `glob()`
- **Shell**: Execute terminal commands
- **Web**: `google_web_search()`, `web_fetch()`
- **Memory**: `save_memory()` for cross-session recall

</v-clicks>

```bash
# The agent automatically uses appropriate tools
"Search the web for React 19 new features"
# Uses google_web_search()

"Read all Python files in src/"
# Uses glob() and read_file()

"Update the README with the changes we made"
# Uses write_file()
```

---
layout: image-right
image: https://images.unsplash.com/photo-1488590528505-98d2b5aba04b?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80
backgroundSize: cover
---

# Safety & Control

<div class="mt-20">
  <h2 class="text-4xl font-bold text-white bg-black bg-opacity-60 px-6 py-3 rounded-lg">
    Work Safely
  </h2>
  <p class="text-xl text-white bg-black bg-opacity-60 px-4 py-2 rounded mt-4">
    Permission rules and sandboxing
  </p>
</div>

---

# Tool Permissions

<v-clicks>

- **Default**: prompt for approval on each tool call
- **`/permissions`**: add, edit, or remove allow/deny rules in-CLI
- **`proceed-in-sandbox`**: auto-approve commands that stay in the sandbox
- **`--dangerously-skip-permissions`**: auto-approve everything (use with care)

</v-clicks>

```bash
# Default - interactive, prompts per tool call
agy

# Auto-approve all tool calls (use with care)
agy --dangerously-skip-permissions

# Manage allow/deny rules from inside a session
> /permissions
```

---

# Artifact Review

<v-clicks>

- Review proposed changes before they are applied
- Open the **Artifact Review panel** with `Ctrl+R`
- Inspect diffs with `/diff` (supports commit-hash selection)
- Works even while answering pending tool-permission prompts
- Great safety habit when exploring an unfamiliar codebase

</v-clicks>

```bash
# Inspect changes from inside a session
> /diff

# Toggle the Artifact Review panel
Ctrl+R
```

---

# Sandbox Mode

<v-clicks>

- Isolate file operations away from your host
- Multiple backends depending on your OS
- Prevents accidental system changes
- Perfect for exploring unfamiliar code

</v-clicks>

```bash
# Run in sandbox mode (terminal restrictions enabled)
agy --sandbox

# Combine with a one-shot prompt
agy --sandbox -p "Refactor this entire codebase"
```

---

# Sandbox & Permission Modes

<v-clicks>

- **`--sandbox`**: run with terminal restrictions enabled
- **`proceed-in-sandbox`** permission mode: auto-approve commands that
  stay inside the sandbox, prompt only when one tries to break out
- Sandbox isolation is enforced in headless print mode too (`-p`)
- Pair with `/permissions` rules for durable guardrails

</v-clicks>

```bash
# Interactive, sandboxed
agy --sandbox

# Non-interactive, sandbox still enforced
agy --sandbox -p "Audit @./src for risky calls"
```

📖 [antigravity.google/docs](https://antigravity.google/docs)

---

# Checkpointing

<v-clicks>

- **Snapshots**: capture state before file modifications
- **Shadow storage**: kept under `~/.gemini/` (not your repo)
- **Includes**: files + conversation + tool call
- **Manage** checkpoints from the `/context` panel

</v-clicks>

```bash
# View context and manage checkpoints
> /context
```

---

# Restoring Checkpoints

```bash
# Open the context panel to review checkpoints
/context

# Resume an earlier conversation by ID
agy --conversation <id>

# Continue the most recent conversation
agy -c
```

Recover earlier state and pick up where you left off

---
layout: image-left
image: https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80
backgroundSize: cover
---

# Context Management

<div class="text-center mt-20">
  <h2 class="text-4xl font-bold text-white bg-black bg-opacity-60 px-6 py-3 rounded-lg">
    AGENTS.md Files
  </h2>
  <p class="text-xl text-white bg-black bg-opacity-60 px-4 py-2 rounded mt-4">
    Project memory and instructions
  </p>
</div>

---

# What is AGENTS.md?

<v-clicks>

- **Project memory** loaded automatically
- **Coding standards** and conventions
- **Architecture context** for the AI
- **Persistent instructions** across sessions
- Antigravity also recognizes `GEMINI.md` and `CLAUDE.md`

</v-clicks>

---

# Hierarchical Loading

```mermaid
graph TD
    A[~/.gemini/AGENTS.md<br/>Global Rules] --> B[project/AGENTS.md<br/>Project Standards]
    B --> C[project/frontend/AGENTS.md<br/>Frontend Conventions]
    B --> D[project/backend/AGENTS.md<br/>Backend Patterns]

    style A fill:#FFE5CC,stroke:#333,stroke-width:2px,color:#000
    style B fill:#CCE5FF,stroke:#333,stroke-width:2px,color:#000
    style C fill:#E5CCFF,stroke:#333,stroke-width:2px,color:#000
    style D fill:#CCFFE5,stroke:#333,stroke-width:2px,color:#000
```

More specific files override general ones

---

# Example AGENTS.md

```markdown
# Project: Weather API
## Tech Stack
- Backend: Python Flask
- Database: PostgreSQL
- Testing: pytest
## Coding Standards
- Use type hints for all functions
- Follow PEP 8 style guide
- Write docstrings for public APIs
## Current Focus
Implementing caching layer for API responses
```

---

# Managing Context

<v-clicks>

- Edit `AGENTS.md` directly to update project memory
- `/context` - view combined context and token usage
- Add `includeDirectories` in settings to load shared context
- Restart or reload the session to pick up changes

</v-clicks>

```bash
# Create or edit project memory
$EDITOR AGENTS.md

# See what context is loaded
> /context
```

---

# Modular Imports

<v-clicks>

- Import other files with `@file.md` syntax
- Break large context into components
- Supports relative and absolute paths

</v-clicks>

```markdown
# AGENTS.md

## Project Overview
@./docs/architecture.md

## Coding Standards
@./docs/style-guide.md

## API Documentation
@./docs/api-reference.md
```

---
layout: image-right
image: https://images.unsplash.com/photo-1558494949-ef010cbdcc31?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80
backgroundSize: cover
---

# Configuration

<div class="mt-20">
  <h2 class="text-4xl font-bold text-white bg-black bg-opacity-60 px-6 py-3 rounded-lg">
    Customize Your Setup
  </h2>
  <p class="text-xl text-white bg-black bg-opacity-60 px-4 py-2 rounded mt-4">
    settings.json and environment
  </p>
</div>

---

# Configuration Layers

<v-clicks>

1. **Default values** - Built-in defaults
2. **User settings** - `~/.gemini/settings.json`
3. **Project settings** - `.gemini/settings.json`
4. **Environment variables** - Including `.env` files
5. **Command-line arguments** - Highest priority

</v-clicks>

---

# settings.json Options

```json
{
  "general": {
    "preferredEditor": "vscode",
    "vimMode": false,
    "checkpointing": { "enabled": true }
  }
}
```

---

# settings.json Options (UI + Tools)

```json
{
  "ui": {
    "hideTips": false,
    "hideBanner": false
  },
  "tools": {
    "sandbox": false
  }
}
```

---

# Tool Permissions & Rules

<v-clicks>

- **`/permissions`**: add, edit, or remove allow/deny rules in-CLI
- Rules merge across three layers: project, user, and CLI settings
- Shared with the Antigravity desktop app's permission settings
- Keep high-risk tools constrained for teams

</v-clicks>

```bash
# Manage permission rules interactively
> /permissions

# Auto-approve everything (use with care)
agy --dangerously-skip-permissions
```

📖 [antigravity.google/docs](https://antigravity.google/docs)

---

# File Filtering

<v-clicks>

- **respectGitIgnore**: Honor .gitignore patterns
- **enableRecursiveFileSearch**: Recursive completion
- Exclude rules and allowlists live in `rules.json`

</v-clicks>

```json
{
  "context": {
    "fileFiltering": {
      "respectGitIgnore": true,
      "enableRecursiveFileSearch": true
    }
  }
}
```

---

# Environment Variables

| Variable | Purpose |
|----------|---------|
| `ANTIGRAVITY_API_KEY` | API-key authentication (alternative to sign-in) |
| `AGY_CLI_DISABLE_LATEX` | Turn off LaTeX math rendering |
| `AGY_CLI_HIDE_ACCOUNT_INFO` | Hide email and plan tier from the header |
| `$EDITOR` | External editor for prompts and files |
| `HTTP_PROXY` | Network proxy |

---

# Custom Context Filenames

<v-clicks>

- **`AGENTS.md`** is the documented default context file
- `GEMINI.md` and `CLAUDE.md` are also recognized
- Support multiple filenames in priority order
- Include additional directories for shared context

</v-clicks>

```json
{
  "context": {
    "fileName": ["AGENTS.md", "GEMINI.md", "CLAUDE.md"],
    "includeDirectories": ["~/shared-context"],
    "loadMemoryFromIncludeDirectories": true
  }
}
```

---
layout: image-right
image: https://images.unsplash.com/photo-1516321318423-f06f85e504b3?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80
backgroundSize: cover
---

# Advanced Features

<div class="mt-20">
  <h2 class="text-4xl font-bold text-white bg-black bg-opacity-60 px-6 py-3 rounded-lg">
    Power User Tools
  </h2>
  <p class="text-xl text-white bg-black bg-opacity-60 px-4 py-2 rounded mt-4">
    MCP, Plugins, Sessions
  </p>
</div>

---

# Model Context Protocol (MCP)

<v-clicks>

- Standard protocol for AI-to-system connections
- Connect to external tools and services
- Supports local commands, HTTP, and SSE
- OAuth 2.0 for remote authentication

</v-clicks>

---

# MCP Configuration: Firecrawl

```json
{
  "mcpServers": {
    "firecrawl": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-firecrawl"],
      "env": {
        "FIRECRAWL_API_KEY": "${FIRECRAWL_API_KEY}"
      }
    }
  }
}
```

---

# MCP Configuration: Database

```json
{
  "mcpServers": {
    "postgres": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-postgres"],
      "env": {
        "CONNECTION_STRING": "${DATABASE_URL}"
      }
    }
  }
}
```

---

# Managing MCP Servers

Antigravity has no `mcp` subcommand — edit the config file directly:

```bash
# Open the MCP config
$EDITOR ~/.gemini/config/mcp_config.json
```

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"]
    }
  }
}
```

Servers initialize in parallel on startup.

---

# MCP: Remote Servers

Use a `url` for HTTP/remote MCP servers (added in 1.0.5):

```json
{
  "mcpServers": {
    "remote-tools": {
      "url": "https://mcp.example.com/sse"
    }
  }
}
```

Toggle servers from the in-CLI settings; changes reload on restart.

---

# MCP Server Options

<v-clicks>

- **command**: Shell command to start server
- **args**: Command arguments
- **env**: Environment variables
- **cwd**: Working directory

</v-clicks>

---

# MCP Server Options (Advanced)

<v-clicks>

- **timeout**: Startup timeout in ms
- **includeTools/excludeTools**: Filter available tools
- **trust**: Bypass tool confirmation for this server

</v-clicks>

---

# Popular MCP Servers

<v-clicks>

- **Firecrawl** - Web scraping, search, content extraction
- **PostgreSQL** - Database queries and schema
- **Filesystem** - Extended file operations
- **Slack** - Team communication
- **Playwright** - Browser automation

</v-clicks>

📖 **Registry**: [modelcontextprotocol.io/registry](https://modelcontextprotocol.io/registry)

---

# Plugins from Marketplaces

<v-clicks>

- Install from a marketplace with `plugin@marketplace` syntax
- Plugins bundle **skills** and **subagents**, discovered automatically
- Import existing Gemini or Claude plugins with `agy plugin import`
- Plugins install to the shared `~/.gemini/config/` directory

</v-clicks>

```bash
# Install, then link a marketplace
agy plugin install my-plugin@my-marketplace
agy plugin link my-marketplace ./target
```

📖 [antigravity.google/docs](https://antigravity.google/docs)

---

# Subagents

<v-clicks>

- Dispatch focused tasks to a **subagent** with `/agent <task>`
- Subagents run with their own context and interaction timeout
- Bundled and discovered through installed plugins
- Standalone subagent conversations stay separate in `/resume`

</v-clicks>

```bash
# Dispatch an async subagent
> /agent write unit tests for @./src/utils.py
```

---

# Plugin System

<v-clicks>

- Extend Antigravity CLI with **plugins** (skills + subagents)
- Managed with the `agy plugin` subcommand
- Import from Gemini or Claude: `agy plugin import gemini`
- Installed plugins are scanned for skills and agents automatically

</v-clicks>

```bash
# List installed plugins
agy plugin list

# Install / enable / disable
agy plugin install my-plugin@marketplace
agy plugin enable my-plugin
agy plugin disable my-plugin
```

---

# Skills

<v-clicks>

- Package reusable expert workflows as **skills**
- Distributed inside plugins, stored under `~/.gemini/config/skills/`
- Surface as slash commands via autocomplete
- Discovered automatically from installed plugins

</v-clicks>

```bash
# Skills arrive with plugins
agy plugin install code-review@marketplace

# Invoke a skill-derived command in-session
> /code-review @./src
```

---

# Session Management

<v-clicks>

- **Continue**: pick up the most recent conversation
- **Resume by ID**: jump to a specific past conversation
- **Browse**: open the conversation picker with `/resume`
- Conversations are stored in SQLite (`.db`)

</v-clicks>

```bash
# Continue the most recent conversation
agy -c

# Resume a specific conversation by ID
agy --conversation <id>

# Browse conversations from inside a session
> /resume
```

---

# Non-Interactive (Print) Mode

<v-clicks>

- **`-p` / `--print`**: run a single prompt and print the response
- **`--print-timeout`**: bound how long print mode waits (default 5m)
- Sandbox isolation is enforced in print mode too
- Pipe input from other commands for scripting

</v-clicks>

```bash
# One-shot print mode
agy -p "List all TODO comments in @./src"

# Piped input
cat error.log | agy -p "Diagnose this stack trace"
```

---

# Desktop Integration

<v-clicks>

- **Antigravity 2.0 desktop app**: shares config and conversations
- **`/export`**: push a CLI session into the desktop app
- **Shared permissions**: rules carry across CLI and desktop
- **External editor**: set `$EDITOR` for prompt and file editing

</v-clicks>

```bash
# Push this session to the desktop app
> /export
```

---
layout: image-left
image: https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80
backgroundSize: cover
---

# Practical Applications

<div class="mt-20">
  <h2 class="text-4xl font-bold text-white bg-black bg-opacity-70 px-6 py-3 rounded-lg">
    Real-World Workflows
  </h2>
  <p class="text-xl text-white bg-black bg-opacity-70 px-4 py-2 rounded mt-4">
    Common use cases
  </p>
</div>

---

# Code Exploration

<v-clicks>

- Understand unfamiliar codebases
- Trace dependencies and data flow
- Find patterns and conventions
- Generate architecture documentation

</v-clicks>

```bash
agy -p "Analyze the architecture of @./src/ and explain
how the components interact"

agy -p "Trace the flow from the API endpoint to the database
in @./src/controllers/ and @./src/services/"
```

---

# Test Generation

<v-clicks>

- Generate unit tests for existing code
- Identify edge cases automatically
- Create integration test scaffolding
- Mock setup and fixtures

</v-clicks>

```bash
agy -p "Create comprehensive unit tests for @./src/utils.py
with pytest, including edge cases"

agy -p "Generate integration tests for @./src/api/users.py
with proper mocking"
```

---

# Documentation Generation

<v-clicks>

- README files for projects
- API documentation
- Architecture diagrams (Mermaid)
- Code comments and docstrings

</v-clicks>

```bash
agy -p "Generate a comprehensive README.md for this project"

agy -p "Add detailed docstrings to all public functions
in @./src/services/"

agy -p "Create a Mermaid diagram showing the system architecture"
```

---

# Refactoring & Modernization

<v-clicks>

- Upgrade legacy code patterns
- Apply modern language features
- Improve code organization
- Fix anti-patterns

</v-clicks>

```bash
agy -p "Refactor @./src/legacy.py to use modern Python 3.12
features like type hints and match statements"

agy -p "Convert this callback-based code to async/await
@./src/api.js"
```

---

# Debugging Workflows

<v-clicks>

- Analyze error messages and stack traces
- Identify root causes
- Suggest fixes with context
- Test and verify solutions

</v-clicks>

```bash
agy -p "This test is failing with @./tests/output.log.
Analyze the error and fix the issue in @./src/app.py"

agy -p "Debug why the API returns 500 errors.
Check @./src/routes.py and @./src/middleware.py"
```

---

# Git Workflows

<v-clicks>

- Generate commit messages
- Create pull request descriptions
- Analyze diffs and changes
- Resolve merge conflicts

</v-clicks>

```bash
# Analyze staged changes
!git diff --staged
"Generate a conventional commit message for these changes"

# Create PR description
"Create a pull request description summarizing the changes
from the last 5 commits"
```

---

# CI/CD Integration

<v-clicks>

- Non-interactive `--print` mode for pipelines
- Capture stdout to a file for parsing
- Exit codes for success/failure
- Automated code reviews

</v-clicks>

```bash
# In CI/CD pipeline
agy -p "Review @./src/ for security issues" > review.txt

# Check exit code
if agy -p "Verify all tests pass"; then
  echo "All checks passed"
fi
```

---
layout: image-right
image: https://images.unsplash.com/photo-1522071820081-009f0129c71c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80
backgroundSize: cover
---

# Optional Advanced Module

<v-clicks>

- Designed for teams moving from personal usage to production workflows
- Can be taught live or assigned as follow-up practice
- Focus areas: auth strategy, governance, skills/MCP, CI automation

</v-clicks>

---

# Authentication Matrix (Team Use)

<v-clicks>

- **Google Sign-In**: best default for local interactive usage
- **Device-code flow**: shows a URL + code for remote/SSH machines
- **`ANTIGRAVITY_API_KEY`**: scripts and headless automation
- **G1 credits**: keep teams productive past standard quota

</v-clicks>

---

# Auth Quick Checks

```bash
# Interactive route: sign in with Google on first run
agy

# API-key route (scripts / headless)
export ANTIGRAVITY_API_KEY="..."
agy -p "Summarize @./src"

# Hide account info from the header (e.g. for screen sharing)
export AGY_CLI_HIDE_ACCOUNT_INFO=1
agy
```

---

# Governance: Permissions and Rules

<v-clicks>

- `--dangerously-skip-permissions` is a per-session escape hatch
- `/permissions` rules provide durable guardrails across users/projects
- Keep high-risk tools constrained in team settings
- Prefer explicit allow/deny patterns over ad-hoc approvals

</v-clicks>

---

# Governance: Folder Trust

<v-clicks>

- Antigravity tracks trusted folders (`trustedFolders.json`)
- Folder trust impacts settings, skills, and context loading
- Treat untrusted repos with `--sandbox` and stricter rules
- Combine with `/permissions` for auditable guardrails

</v-clicks>

---

# Skills + MCP at Scale

<v-clicks>

- Skills package repeatable expert workflows for teams
- MCP connects external systems (docs, data, browsers, APIs)
- Distribute skills and subagents together inside plugins
- Use `includeTools`/`excludeTools` to narrow risky MCP exposure

</v-clicks>

---

# Plugins + MCP Commands

```bash
# Plugin (skills + subagents) lifecycle
agy plugin list
agy plugin disable my-plugin
agy plugin enable my-plugin

# MCP servers: edit config, then restart to reload
$EDITOR ~/.gemini/config/mcp_config.json
```

---

# Automation Patterns (Non-Interactive)

<v-clicks>

- Prefer `--print` for non-interactive runs
- Use exit codes for pipeline gates
- Keep prompts deterministic and repo-scoped
- Store logs/artifacts for auditability

</v-clicks>

---

# CI Example: Gate + Report

```bash
agy -p "Review @./src/ for security issues" > review.txt

if agy -p "Run checks and report pass/fail"; then
  echo "Gate passed"
else
  echo "Gate failed" && exit 1
fi
```

---
layout: image-right
image: https://images.unsplash.com/photo-1522071820081-009f0129c71c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80
backgroundSize: cover
---

# Best Practices

<div class="text-center mt-20">
  <h2 class="text-4xl font-bold text-white bg-black bg-opacity-60 px-6 py-3 rounded-lg">
    Professional Workflows
  </h2>
  <p class="text-xl text-white bg-black bg-opacity-60 px-4 py-2 rounded mt-4">
    Tips for success
  </p>
</div>

---

# Effective Prompting

<v-clicks>

- **Be specific** about what you want to achieve
- **Provide context** about goals and constraints
- **Use file references** to ground the conversation
- **Iterate** for complex tasks
- **Include examples** when possible

</v-clicks>

---

# Safety Guidelines

<v-clicks>

- **Start in default mode** - Get comfortable first
- **Enable checkpointing** - Safety net for mistakes
- **Review generated code** - Don't blindly accept
- **Use sandbox** for exploratory work
- **Commit often** - Git is your safety net

</v-clicks>

---

# Project Setup

<v-clicks>

1. Create a comprehensive AGENTS.md
2. Set up project-specific settings.json
3. Configure relevant MCP servers
4. Create custom commands for common tasks
5. Establish team conventions

</v-clicks>

---

# AGENTS.md Best Practices

<v-clicks>

- **Keep it focused** - Relevant project info only
- **Update regularly** - Reflect current state
- **Use imports** - Modularize large contexts
- **Include examples** - Show expected patterns
- **Document conventions** - Style guides, patterns

</v-clicks>

---

# Team Collaboration

<v-clicks>

- Share AGENTS.md in version control
- Standardize settings.json across team
- Create shared custom commands
- Document AI-assisted workflows
- Review AI-generated code together

</v-clicks>

---

# Common Pitfalls

<v-clicks>

- **Overly broad prompts** → Be specific
- **Missing context** → Use AGENTS.md
- **Skipping review** → Always verify output
- **Skipping permissions** → Don't reach for `--dangerously-skip-permissions` early
- **Ignoring Artifact Review** → Inspect diffs before applying

</v-clicks>

---

# Troubleshooting

<v-clicks>

- **Authentication issues**: Re-run `agy` to sign in, or check `ANTIGRAVITY_API_KEY`
- **Rate limits**: Check `/quota`; G1 credits cover overflow
- **Tool failures**: Verify `mcp_config.json` and server status
- **Context not loading**: Confirm `AGENTS.md` location, reload session
- **Logs**: Override the log path with `--log-file`

</v-clicks>

```bash
# Write logs to a known path for troubleshooting
agy --log-file ./agy.log

# Inspect loaded context and token usage
> /context
```

---

# Quick Access

<div class="grid grid-cols-2 gap-8 mt-8 place-items-center">
  <div class="flex flex-col items-center">
    <h3>Antigravity CLI Docs</h3>
    <QRCode
      :width="200"
      :height="200"
      type="svg"
      data="https://antigravity.google/docs"
      :margin="5"
      :dotsOptions="{ type: 'rounded', color: '#3b82f6' }"
    />
    <p class="text-sm mt-2">antigravity.google/docs</p>
  </div>
  <div class="flex flex-col items-center">
    <h3>Course Repository</h3>
    <QRCode
      :width="200"
      :height="200"
      type="svg"
      data="https://github.com/kousen/gemini-training"
      :margin="5"
      :dotsOptions="{ type: 'rounded', color: '#10b981' }"
    />
    <p class="text-sm mt-2">github.com/kousen/gemini-training</p>
  </div>
</div>

---

# Important Links

<div class="mt-8 space-y-6 text-xl">

<v-clicks>

### 📚 Official Documentation
`https://antigravity.google/docs`

### 💾 Source Repository
`https://github.com/google-antigravity/antigravity-cli`

### 📦 MCP Server Registry
`https://modelcontextprotocol.io/registry`

### 💻 Course Materials
`https://github.com/kousen/gemini-training`

</v-clicks>

</div>

---

# Command Reference: Basic Usage

```bash
# Interactive mode
agy

# One-shot (print) mode
agy -p "prompt"

# Interactive with initial prompt
agy -i "context"
```

---

# Command Reference: Safety

```bash
# Run in sandbox mode
agy --sandbox

# Auto-approve all tool calls (use with care)
agy --dangerously-skip-permissions

# Manage permission rules in-session
> /permissions
```

---

# Command Reference: Sessions

```bash
# Continue the most recent conversation
agy -c

# Resume a conversation by ID
agy --conversation <id>

# Browse conversations in-session
> /resume
```

---

# Command Reference: Output

```bash
# Print mode for scripting
agy -p "prompt"

# Bound how long print mode waits
agy --print-timeout 2m -p "prompt"

# Write logs to a file
agy --log-file ./agy.log
```

---

# Thank You!

<div class="text-center">

## Questions?

<div class="pt-12">
  <span class="text-6xl"><carbon:logo-github /></span>
</div>

**Kenneth Kousen**
*Author, Speaker, Java & AI Expert*

[kousenit.com](https://kousenit.com) | [@kenkousen](https://twitter.com/kenkousen)

</div>
