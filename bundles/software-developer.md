---
bundle:
  name: software-developer
  version: 2.0.0
  description: Development configuration with full toolset
  instruction_compose_mode: append  # Accumulate all bundle instructions

includes:
  # Base capabilities (Foundation provides tools, hooks, agents)
  - bundle: git+https://github.com/microsoft/amplifier-foundation@main
  # Additional behaviors
  - bundle: payne-amplifier:behaviors/web
  - bundle: foundation:behaviors/logging
  - bundle: foundation:behaviors/streaming-ui
  - bundle: foundation:behaviors/redaction
  # Primary behavior LAST (all instructions accumulate with append mode)
  - bundle: payne-amplifier:behaviors/software-development

providers:
  - module: provider-anthropic
    source: git+https://github.com/microsoft/amplifier-module-provider-anthropic@main
    config:
      default_model: claude-opus-4-5
      max_tokens: 16384
---
