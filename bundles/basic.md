---
bundle:
  name: basic
  version: 1.2.0
  description: Basic assistant configuration with core functionality, tools, and hooks

session:
  orchestrator:
    module: loop-streaming
    source: git+https://github.com/microsoft/amplifier-module-loop-streaming@main
    config:
      extended_thinking: true
  context:
    module: context-simple
    source: git+https://github.com/microsoft/amplifier-module-context-simple@main
    config:
      max_tokens: 400000
      compact_threshold: 0.8
      auto_compact: true

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
  - module: explorer
    source: git+https://github.com/microsoft/amplifier-module-agent-explorer@main
  - module: post-task-cleanup
    source: git+https://github.com/microsoft/amplifier-module-agent-post-task-cleanup@main

context:
  foundation: ./contexts/foundation
  lakehouse: ./contexts/lakehouse
---

# Basic Assistant

You are an AI assistant powered by Amplifier.

@lakehouse:lakehouse.md
@foundation:common-profile-base.md
