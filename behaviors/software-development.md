---
bundle:
  name: behavior-software-development
  version: 1.0.0
  description: Software development capabilities with agents and context

includes:
  - bundle: payne-amplifier:behaviors/command-line
  - bundle: payne-amplifier:behaviors/task-management

hooks:
  - module: hooks-status-context
    source: git+https://github.com/microsoft/amplifier-module-hooks-status-context@main
    config:
      datetime_include_timezone: false
      git_include_branch: true
      git_include_commits: 5
      git_include_main_branch: true
      git_include_status: true
      include_datetime: true
      include_git: true

agents:
  - module: bug-hunter
    source: git+https://github.com/microsoft/amplifier-module-agent-bug-hunter@main
  - module: explorer
    source: git+https://github.com/microsoft/amplifier-module-agent-explorer@main
  - module: modular-builder
    source: git+https://github.com/microsoft/amplifier-module-agent-modular-builder@main
  - module: post-task-cleanup
    source: git+https://github.com/microsoft/amplifier-module-agent-post-task-cleanup@main
  - module: zen-architect
    source: git+https://github.com/microsoft/amplifier-module-agent-zen-architect@main
  - module: researcher
    source: git+https://github.com/microsoft/amplifier-module-agent-researcher@main
---

# Software Development Instructions

Key agents you should ALWAYS use:

- zen-architect - analyzes problems, designs architecture, and reviews code quality.
- modular-builder - implements code from specifications following modular design principles.
- bug-hunter - identifies and fixes bugs in the codebase.
- post-task-cleanup - ensures the workspace is tidy and all temporary files are removed.

Additional specialized agents available based on task needs:

- test-coverage - ensures comprehensive test coverage.
- database-architect - for database design and optimization.
- security-guardian - for security reviews and vulnerability assessment.
- api-contract-designer - for API design and specification.
- performance-optimizer - for performance analysis and optimization.
- integration-specialist - for external integrations and dependency management.

## Agent Review and Validation Cycles

### Architecture-Implementation-Review Pattern

For complex tasks, use this three-phase cycle:

1. **Architecture Phase**: zen-architect designs the approach
2. **Implementation Phase**: modular-builder, api-contract-designer, etc. implement
3. **Validation Phase**: Return to architectural agents for compliance review
4. **Testing Phase**: Run it like a user, if any issues discovered then leverage bug-hunter

### When to Loop Back for Validation

- After modular-builder completes implementation → zen-architect reviews for philosophy compliance
- After multiple agents complete work → zen-architect reviews overall approach
- After api-contract-designer creates contracts → zen-architect validates modular design
- Before post-task-cleanup → architectural agents confirm no compromises were made
