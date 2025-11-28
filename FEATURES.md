# FEATURES.md

> A simple, open format for documenting project features — designed for both humans and AI coding agents.

## What is FEATURES.md?

FEATURES.md is a markdown file that describes the specifications for features in a project. Think of it as a living requirements document that serves two purposes:

1. **For Humans**: A clear, readable document outlining what the project does and its roadmap
2. **For Agents**: A structured format that AI coding agents can parse to understand feature requirements and implementation status

## Core Principles

### 1. Testable Properties

Every feature property should be **testable**. This means:

- Each feature should have clear acceptance criteria
- Properties should be measurable or verifiable
- Test cases should be derivable from the feature specification

### 2. Stability Levels

Every feature must have a stability indicator:

| Stability | Description |
|-----------|-------------|
| `stable` | Feature is complete, tested, and ready for production use |
| `in-progress` | Feature is currently being developed |
| `planned` | Feature is on the roadmap but work has not started |

## File Structure

A FEATURES.md file should be placed at the root of your repository. Here's the recommended structure:

```markdown
# Project Name - Features

## Overview
Brief description of the project and its purpose.

## Features

### Feature Name
- **Stability**: stable | in-progress | planned
- **Description**: What this feature does
- **Properties**:
  - Property 1 (testable criterion)
  - Property 2 (testable criterion)
- **Test Criteria**:
  - [ ] Test case 1
  - [ ] Test case 2
- **Dependencies**: List any dependencies
- **Notes**: Additional context for agents

### Another Feature
...
```

## Example FEATURES.md

```markdown
# My App - Features

## Overview
A task management application with real-time collaboration.

## Features

### User Authentication
- **Stability**: stable
- **Description**: Secure user registration and login system
- **Properties**:
  - Users can register with email and password
  - Passwords are hashed using bcrypt with salt rounds >= 10
  - Session tokens expire after 24 hours
  - Failed login attempts are rate-limited to 5 per minute
- **Test Criteria**:
  - [x] Registration creates user in database
  - [x] Login returns valid JWT token
  - [x] Invalid credentials return 401
  - [x] Rate limiting blocks after 5 failed attempts

### Real-time Collaboration
- **Stability**: in-progress
- **Description**: Multiple users can edit the same document simultaneously
- **Properties**:
  - Changes sync within 100ms
  - Conflict resolution uses CRDT
  - Offline changes queue and sync when reconnected
- **Test Criteria**:
  - [x] Two users see same content
  - [ ] Offline mode queues changes
  - [ ] Reconnection syncs pending changes

### AI Task Suggestions
- **Stability**: planned
- **Description**: AI-powered suggestions for task prioritization
- **Properties**:
  - Analyzes task history and patterns
  - Provides priority recommendations
  - Learns from user feedback
- **Test Criteria**:
  - [ ] Suggestion endpoint returns ranked tasks
  - [ ] Feedback updates model weights
```

## Best Practices

### For Humans

1. **Keep it updated**: Update FEATURES.md as features evolve
2. **Be specific**: Vague properties lead to vague implementations
3. **Include context**: Help readers understand *why* a feature exists
4. **Link to issues**: Reference GitHub issues or tickets when relevant

### For Agents

1. **Parse stability first**: Know what's done, what's in progress, and what's planned
2. **Check test criteria**: Completed tests indicate working functionality
3. **Respect dependencies**: Don't modify stable features without checking impact
4. **Use properties as specs**: They define exact behavior to implement

## Integration with Other Standards

FEATURES.md works well alongside:

- **README.md**: High-level project overview
- **AGENTS.md**: AI agent-specific coding guidelines
- **CONTRIBUTING.md**: Contribution guidelines
- **CHANGELOG.md**: Version history

## Machine-Readable Extensions

For enhanced agent parsing, you can include YAML frontmatter:

```markdown
---
version: 1.0.0
last_updated: 2024-01-15
total_features: 12
stable: 8
in_progress: 3
planned: 1
---

# Project Features
...
```

## Collaborate

We'd love your input on improving the FEATURES.md specification!

- **Signal**: pierce.403
- **GitHub**: Open an issue or submit a PR

---

*FEATURES.md is an open specification. Use it, adapt it, and help make agentic programming more effective.*
