# Antigravity CLI Training Course

A comprehensive training course for mastering Google's Antigravity CLI (`agy`) - the AI coding agent that brings Gemini, Claude, and open models directly into your terminal.

## Course Overview

This 5-hour hands-on workshop covers everything from basic installation to advanced MCP configurations, plugins, and enterprise workflows.

### What You'll Learn

- **Installation & Setup**: Authentication strategies, environment configuration
- **Core Commands**: Interactive mode, one-shot prompts, file references
- **Context Management**: AGENTS.md files, hierarchical context loading
- **Safety & Control**: Sandbox mode, permission rules, Artifact Review
- **Advanced Features**: MCP integration, plugins, skills, subagents
- **Practical Skills**: Real-world exercises in Python, JavaScript, and Java

## Prerequisites

- Command-line experience
- Basic programming knowledge in at least one language
- Git familiarity
- Google account for sign-in (or an `ANTIGRAVITY_API_KEY`)
- Node.js 18+ (only needed to run the Slidev presentation locally)

## Repository Structure

```
gemini-training/
├── slides.md                     # Slidev presentation
├── lab_handout.md               # Progressive hands-on labs
├── exercises/                    # Hands-on lab projects
│   ├── python/                  # Python projects
│   │   └── weather-app/         # Flask weather application
│   ├── javascript/              # JavaScript/TypeScript projects
│   │   └── task-manager/        # Node.js task manager
│   └── java/                    # Java projects
│       └── bookstore-api/       # Spring Boot REST API
├── config-examples/              # Sample configurations
│   ├── settings-basic.json      # Starter settings
│   ├── settings-advanced.json   # Full-featured settings
│   ├── settings-safe.json       # Safety-focused settings
│   └── settings-mcp.json        # MCP-focused settings
├── gemini-md-examples/          # GEMINI.md templates
│   ├── python-flask.md          # Python Flask template
│   ├── java-spring.md           # Spring Boot template
│   └── javascript-react.md      # React project template
└── commands/                     # Custom command examples
    ├── review.toml              # Code review command
    └── test-gen.toml            # Test generation command
```

## Quick Start

### 1. Install Antigravity CLI

```bash
# macOS / Linux (installs the `agy` binary to ~/.local/bin)
curl -fsSL https://antigravity.google/cli/install.sh | bash

# Verify installation
agy --version
```

### 2. Authenticate

```bash
# First run launches Google Sign-In automatically
agy

# Or use an API key for scripts / headless use
export ANTIGRAVITY_API_KEY="your-api-key"
```

### 3. Run Your First Command

```bash
agy -p "Hello! What can you help me with?"
```

### 4. Start the Training

```bash
# Clone this repository
git clone https://github.com/kousen/gemini-training
cd gemini-training

# Install dependencies for slides
npm install

# Start the presentation
npm run dev

# Open browser to http://localhost:3030
```

## Course Schedule

| Section | Duration |
|---------|----------|
| Introduction & Setup | 10 min |
| Installation & Prerequisites | 15 min |
| Authentication & Account Setup | 10 min |
| First Steps & Basic Interface | 15 min |
| Core Commands & Functionality | 65 min |
| Configuration & Customization | 65 min |
| Advanced Features & Extensions | 65 min |
| Practical Applications & Workflows | 45 min |
| Wrap-up & Q&A | 15 min |

## Key Antigravity CLI Features Covered

### Core Features
- Interactive REPL and one-shot (`-p`) modes
- File references with `@` syntax
- Shell integration with `!` prefix
- Sandbox mode for safe execution
- Multi-model: Gemini, Claude, and GPT-OSS via `/model`

### Configuration
- AGENTS.md context files (hierarchical)
- settings.json customization
- Permission rules (`/permissions`)
- Plugins and skills

### Advanced Features
- Model Context Protocol (MCP) servers (`mcp_config.json`)
- Plugin system (`agy plugin`)
- Skills and subagents (`/agent`)
- Conversation management (SQLite) and Artifact Review
- Antigravity 2.0 desktop integration (`/export`)

### New in Antigravity CLI 1.0.x
- Initial 1.0.0 release of the Go-based Antigravity CLI
- Multi-model sessions: Gemini, Claude, GPT-OSS via `/model` (1.0.5)
- `models` subcommand + `--model` flag to choose a model (1.0.5)
- `/permissions` to manage tool permission rules in-CLI (1.0.5)
- G1 credits with `/credits`, `/usage`, `/quota` (1.0.3)
- MCP `url` support in `mcp_config.json`; parallel init (1.0.5/1.0.6)
- SQLite conversation format + `/resume`, `--continue` (1.0.4)
- Plugin discovery for skills and subagents (1.0.1)

## Tips for Success

1. **Start with default approval**: Get comfortable before `--dangerously-skip-permissions`
2. **Use AGENTS.md**: Provide context for better, more consistent results
3. **Use Artifact Review**: Inspect diffs (`Ctrl+R`, `/diff`) before accepting
4. **Review Generated Code**: Always verify AI-generated changes
5. **Leverage MCP**: Extend capabilities with custom tools

## Useful Commands Reference

```bash
# Basic usage
agy                                 # Interactive mode
agy -p "prompt"                     # One-shot (print) mode
agy -i "context"                    # Interactive with initial prompt

# Configuration
agy --sandbox                       # Run in sandbox mode
agy --dangerously-skip-permissions  # Auto-approve all actions (use with care)
agy --model "Gemini 3.1 Pro (High)" # Specify a model (see `agy models`)

# Session management
agy -c                              # Continue most recent conversation
agy --conversation <id>             # Resume a specific conversation
```

## Slash Commands

| Command | Description |
|---------|-------------|
| `/help` | Show available commands and shortcuts |
| `/context` | View loaded context and token usage |
| `/model` | Switch the active model mid-session |
| `/settings` | Open settings and preferences |
| `/permissions` | Add/edit/remove tool permission rules |
| `/resume` | Open the conversation browser |
| `/agent <task>` | Dispatch an asynchronous subagent |
| `/export` | Send the session to the desktop app |
| `/diff` | Review changes (supports commit selection) |
| `/usage` · `/credits` · `/quota` | Quota and credit status |

## Resources

- [Official Antigravity CLI Documentation](https://antigravity.google/docs)
- [Antigravity CLI Source Repository](https://github.com/google-antigravity/antigravity-cli)
- [MCP Server Registry](https://modelcontextprotocol.io/registry)
- [Course Slides](./slides.md)
- [Lab Exercises](./lab_handout.md)

## Instructor

**Kenneth Kousen**
- President, Kousen IT, Inc.
- Author & Technical Trainer
- ken.kousen@kousenit.com
- https://www.kousenit.com

## License

This training material is licensed under the MIT License. See [LICENSE](./LICENSE) file for details.

---

**Ready to start?** Run `npm run dev` and navigate to http://localhost:3030!
