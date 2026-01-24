---
bundle:
  name: software-developer
  version: 2.0.0
  description: Development configuration with full toolset

includes:
  - bundle: git+https://github.com/microsoft/amplifier-foundation@main
  - bundle: payne-amplifier:behaviors/software-development
  - bundle: payne-amplifier:behaviors/web
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
