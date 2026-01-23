---
bundle:
  name: software-developer
  version: 1.3.0
  description: Development configuration with full toolset

session:
  orchestrator:
    module: loop-streaming
    source: git+https://github.com/microsoft/amplifier-module-loop-streaming@main
  context:
    module: context-persistent
    source: git+https://github.com/microsoft/amplifier-module-context-persistent@main

providers:
  - module: provider-anthropic
    source: git+https://github.com/microsoft/amplifier-module-provider-anthropic@main
    config:
      default_model: claude-opus-4-5
      max_tokens: 16384
      debug: true
      raw_debug: true

tools:
  - module: tool-filesystem
    source: git+https://github.com/microsoft/amplifier-module-tool-filesystem@main
  - module: tool-bash
    source: git+https://github.com/microsoft/amplifier-module-tool-bash@main
  - module: tool-search
    source: git+https://github.com/microsoft/amplifier-module-tool-search@main
  - module: tool-web
    source: git+https://github.com/microsoft/amplifier-module-tool-web@main
  - module: tool-todo
    source: git+https://github.com/microsoft/amplifier-module-tool-todo@main
  - module: tool-task
    source: git+https://github.com/microsoft/amplifier-module-tool-task@main

hooks:
  - module: hooks-logging
    source: git+https://github.com/microsoft/amplifier-module-hooks-logging@main
  - module: hooks-redaction
    source: git+https://github.com/microsoft/amplifier-module-hooks-redaction@main
  - module: hooks-streaming-ui
    source: git+https://github.com/microsoft/amplifier-module-hooks-streaming-ui@main
  - module: hooks-todo-reminder
    source: git+https://github.com/microsoft/amplifier-module-hooks-todo-reminder@main
  - module: hooks-status-context
    source: git+https://github.com/microsoft/amplifier-module-hooks-status-context@main

agents:
  - module: bug-hunter
    source: git+https://github.com/microsoft/amplifier-module-agent-bug-hunter@main
  - module: explorer
    source: git+https://github.com/microsoft/amplifier-module-agent-explorer@main
  - module: modular-builder
    source: git+https://github.com/microsoft/amplifier-module-agent-modular-builder@main
  - module: post-task-cleanup
    source: git+https://github.com/microsoft/amplifier-module-agent-post-task-cleanup@main
  - module: researcher
    source: git+https://github.com/microsoft/amplifier-module-agent-researcher@main
  - module: zen-architect
    source: git+https://github.com/microsoft/amplifier-module-agent-zen-architect@main

context:
  foundation: ./contexts/foundation
  software-development: ./contexts/software-development
  lakehouse: ./contexts/lakehouse
---

# Software Developer Assistant

You are an AI assistant powered by Amplifier.

@lakehouse:lakehouse.md
@foundation:common-profile-base.md
@software-development:software-development-base.md
