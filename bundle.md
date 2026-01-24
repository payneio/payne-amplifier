---
bundle:
  name: payne-amplifier
  version: 2.0.0
  description: Personal Amplifier bundles and extensions by Paul Payne
  sub_bundles:
    - name: software-developer
      path: bundles/software-developer.md
      description: Development configuration with full toolset
    - name: basic
      path: bundles/basic.md
      description: Basic configuration with minimal toolset

session:
  orchestrator:
    module: loop-streaming
    source: git+https://github.com/microsoft/amplifier-module-loop-streaming@main
  context:
    module: context-simple
    source: git+https://github.com/microsoft/amplifier-module-context-simple@main

providers:
  - module: provider-anthropic
    source: git+https://github.com/microsoft/amplifier-module-provider-anthropic@main
    config:
      default_model: claude-sonnet-4-20250514
      max_tokens: 16384

tools:
  - module: tool-filesystem
    source: git+https://github.com/microsoft/amplifier-module-tool-filesystem@main
  - module: tool-bash
    source: git+https://github.com/microsoft/amplifier-module-tool-bash@main
---

# Payne Amplifier

Personal Amplifier bundles and extensions by Paul Payne.

## Available Bundles

- **software-developer** - Full development configuration with tools, hooks, and agents
- **basic** - Minimal configuration for simple tasks

## Behaviors

Reusable capability add-ons that can be composed into bundles:

- **software-development** - Full software development workflow with agents
- **command-line** - Bash and filesystem tools
- **task-management** - Todo and task tracking
- **web** - Web browsing and search capabilities
- **logging** - Session event logging
- **streaming-ui** - Progressive display hooks
- **redaction** - Sensitive data handling
- **exploration** - Codebase exploration agent
- **amplifier-expert** - Amplifier ecosystem consultant
