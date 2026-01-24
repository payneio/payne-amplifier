---
bundle:
  name: basic
  version: 2.0.0
  description: Basic assistant configuration with core functionality

includes:
  - bundle: git+https://github.com/microsoft/amplifier-foundation@main
  - bundle: payne-amplifier:behaviors/command-line
  - bundle: payne-amplifier:behaviors/web
  - bundle: payne-amplifier:behaviors/task-management
  - bundle: foundation:behaviors/logging
  - bundle: foundation:behaviors/streaming-ui
  - bundle: foundation:behaviors/redaction

providers:
  - module: provider-anthropic
    source: git+https://github.com/microsoft/amplifier-module-provider-anthropic@main
    config:
      default_model: claude-opus-4-5
      max_tokens: 16384
---

# Basic Assistant

You are an AI assistant powered by Amplifier.
