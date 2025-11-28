# FEATURES.md

<p align="center">
  <strong>A simple, open format for documenting project features — designed for both humans and AI coding agents.</strong>
</p>

## What is FEATURES.md?

[FEATURES.md](./FEATURES.md) is a markdown file that describes the specifications for features in a project. Think of it as a README for features: a dedicated, predictable place to document what your project does and what it's working towards.

Just like how `AGENTS.md` provides instructions for AI coding agents, `FEATURES.md` provides a structured way to document:

- **What features exist** and their current state
- **Testable properties** that define expected behavior
- **Stability levels** to indicate production-readiness

## Quick Start

Add a `FEATURES.md` file to your project root:

```markdown
# My Project - Features

## Features

### User Authentication
- **Stability**: stable
- **Description**: Secure login system with JWT tokens
- **Properties**:
  - Passwords are hashed with bcrypt (salt rounds >= 10)
  - Session tokens expire after 24 hours
- **Test Criteria**:
  - [x] Valid credentials return JWT token
  - [x] Invalid credentials return 401

### API Rate Limiting
- **Stability**: in-progress
- **Description**: Prevent API abuse with rate limiting
- **Properties**:
  - 100 requests per minute per user
  - Returns 429 when limit exceeded
- **Test Criteria**:
  - [x] Normal usage succeeds
  - [ ] Excessive requests blocked
```

## Stability Levels

| Level | Description |
|-------|-------------|
| `stable` | Complete, tested, production-ready |
| `in-progress` | Currently being developed |
| `planned` | On the roadmap, not yet started |

## Core Principles

1. **Testable Properties**: Every feature property should be verifiable
2. **Clear Stability**: Always indicate what's ready and what's not
3. **Human & Agent Friendly**: Readable by developers and parseable by AI

## Full Specification

See [FEATURES.md](./FEATURES.md) for the complete specification and more examples.

## Collaborate

We'd love your input on improving the FEATURES.md specification!

- **Signal**: pierce.403
- **GitHub**: Open an issue or submit a PR

---

*Inspired by [AGENTS.md](https://github.com/openai/agents.md) — making agentic programming more effective.*
