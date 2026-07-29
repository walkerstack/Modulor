# Modulor

**An AI + no-code platform for building business systems fast.**

Instead of generating everything from scratch, AI works on top of production-proven infrastructure and a WYSIWYG no-code interface — so you get both speed and reliability.

> **Note:** the npm packages, CLI (`nb`), and internal commands retain their original identifiers, so every command below is copy-paste accurate.

## Table of Contents

- [What It Is](#what-it-is)
- [Quick Start](#quick-start)
- [Distinctive Features](#distinctive-features)
  - [1. Collaborative — AI and people build together](#1-collaborative--ai-and-people-build-together)
  - [2. Intelligent — AI helps run the business](#2-intelligent--ai-helps-run-the-business)
  - [3. Reliable — ready infrastructure for real business](#3-reliable--ready-infrastructure-for-real-business)
- [Repository Structure](#repository-structure)
- [Development](#development)
- [License](#license)

## What It Is

Modulor is a platform for building internal business systems — data models, pages, workflows, and permissions — without starting from scratch each time. Two audiences work on the same system:

- **Coding agents** get a full CLI and a set of skills
- **People** get a visual, WYSIWYG configuration interface

Both operate against the same underlying data model, so work done by either side stays transparent and reversible.

## Quick Start

```bash
# Install the CLI
npm install -g @nocobase/cli
nb --version

# Initialize an app
nb init --ui

# Optional: build alongside an AI coding agent
codex   # or claude, opencode
```

## Distinctive Features

### 1. Collaborative — AI and people build together

Coding agents get a full CLI and skills; people get a WYSIWYG no-code interface. Both can collaborate efficiently on the same system.

**Build with the coding agents you already use**

- Works with mainstream agents such as Claude Code, Cursor, Codex, OpenCode, and TRAE
- Agents can handle setup, development, migration, and release end to end

**Build manually in a WYSIWYG interface**

- Switch between usage mode and configuration mode with one click
- Review and configure data models, pages, workflows, and permissions visually
- Designed for regular users, not just developers

**Mix both approaches however you need**

- AI can quickly create data models, pages, and workflows
- People can refine the UI and interactions
- Either side can pick up where the other left off and keep iterating

### 2. Intelligent — AI helps run the business

The platform includes **AI employees**, so AI can work inside the running system rather than only helping to build it.

**AI employees integrated into business workflows**

- Front-end: analysis, Q&A, form filling, and more
- Back-end: document recognition, risk monitoring, and task routing
- Integrated with workflows, so AI employees can participate in decisions and execution

**Open interfaces for the agent ecosystem**

- MCP, HTTP APIs, CLI, and a rich skill set let external agents connect securely
- Automation platforms connect through standard protocols
- Messaging and email integrations can query data, trigger actions, and run business workflows
- One interface model keeps internal and external agents within the same boundaries

**Permission controls keep AI behavior in check**

- Each AI employee has its own role, with field-level read and write permissions
- Audit logs make every data change and workflow trigger traceable
- Administrators can adjust AI permissions at any time

### 3. Reliable — ready infrastructure for real business

Data models, permissions, and workflows are complex and error-sensitive. They ship as built-in infrastructure, tested in production, rather than being regenerated as black-box code each time.

**Complete infrastructure out of the box**

- Dozens of built-in modules cover the most common business needs
- Data models, permissions, workflows, and audit logs work immediately
- Built-in guardrails keep AI output aligned with the system architecture

**Data-model driven, with data decoupled from the UI**

- Business data stays in standard relational structures, separate from the interface
- Use the main database, external databases, and third-party APIs as data sources
- AI and people work against the same data model, so results stay transparent
- Data stays in your own database — no platform lock-in

**Plugin architecture for sustainable growth**

- A microkernel design where everything is a plugin
- New features are added through composable plugins with shared conventions
- Mix custom and bundled plugins to fit your business
- The same architecture applies to AI-built and manually built plugins

## Repository Structure

This is a Yarn/Lerna monorepo:

```
packages/
├── core/         # Framework core (server, client, database, CLI, ...)
├── plugins/      # Bundled plugins
└── presets/      # Preset plugin bundles
docker/           # Container definitions
docs/             # Documentation source
examples/         # Example applications
benchmark/        # Performance benchmarks
locales/          # Translations
scripts/          # Build and release tooling
storage/          # Runtime storage
```

Localized versions of this document are available as `README.<locale>.md` alongside this file.

## Development

Requires **Node.js 18+**.

```bash
yarn install          # Install dependencies

yarn dev              # Start the development server
yarn dev-server       # Server only

yarn build            # Build for production
yarn start            # Run the production build

yarn test             # Full test suite
yarn test:server      # Server tests
yarn test:client      # Client tests
yarn e2e              # End-to-end tests (Playwright)

yarn pm               # Plugin manager CLI
```

Environment templates are provided as `.env.example`, `.env.test.example`, `.env.e2e.example`, and `.env.perf.example` — copy the relevant one to `.env` before running.

Container-based setup is available via `docker-compose.yml` and the `Dockerfile`.

## License

This project is distributed under the terms in [LICENSE.txt](LICENSE.txt), with third-party components under [LICENSE-APACHE.txt](LICENSE-APACHE.txt). Portions are AGPL-3.0 licensed.

> **Important:** the license agreement places specific restrictions on removing or altering branding, names, links, version numbers, and intellectual-property statements — and grants those rights only under particular license tiers. Review [LICENSE.txt](LICENSE.txt) (sections 5–7) and confirm your tier before rebranding or redistributing this software. Security policy is documented in [SECURITY.md](SECURITY.md).
