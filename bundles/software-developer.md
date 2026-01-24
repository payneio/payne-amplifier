---
bundle:
  name: software-developer
  version: 2.0.0
  description: Development configuration with full toolset

includes:
  # Base capabilities (Foundation provides tools, hooks, agents)
  - bundle: git+https://github.com/microsoft/amplifier-foundation@main
  # Additional behaviors (no instructions, order doesn't matter)
  - bundle: payne-amplifier:behaviors/web
  - bundle: foundation:behaviors/logging
  - bundle: foundation:behaviors/streaming-ui
  - bundle: foundation:behaviors/redaction
  # Primary behavior LAST (its instruction wins via compose "later replaces earlier")
  - bundle: payne-amplifier:behaviors/software-development

providers:
  - module: provider-anthropic
    source: git+https://github.com/microsoft/amplifier-module-provider-anthropic@main
    config:
      default_model: claude-opus-4-5
      max_tokens: 16384
---
