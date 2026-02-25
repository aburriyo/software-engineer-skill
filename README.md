# Software Engineer Skill

A [Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview) skill that acts as your **personal software architect** — it plans new projects from scratch and documents existing codebases, covering the full cycle from idea to implementation-ready scaffold.

## The Problem

Developers skip planning because it feels slow. We jump straight into coding, and pay the price later: missed edge cases, no documentation, poor architecture decisions. When a project already exists without docs, reconstructing them is equally painful.

## The Solution

This skill makes planning as fast and natural as coding. It operates in two modes:

### Prospective Mode (new project)
```
Idea → Guided questions → Engineering documentation → Implementation plan → Scaffold
```

### Retrospective Mode (existing project)
```
Existing code → Automated analysis → Generated documentation → Gaps identified → Improvement plan
```

## What It Generates

Up to 13 selectable engineering documentation sections:

| # | Section | Description |
|---|---------|-------------|
| 01 | System Architecture (C4) | Context and container diagrams |
| 02 | Use Cases | Detailed flows with happy/alt/exception paths |
| 03 | Domain Model | Conceptual class diagram |
| 04 | ER Diagram | Physical database model |
| 05 | API Catalog | Full endpoint contracts |
| 06 | State Diagrams | Entity lifecycle documentation |
| 07 | Requirements | Functional and non-functional |
| 08 | Traceability Matrix | Requirements vs use cases cross-reference |
| 09 | Sequence Diagrams | Component interaction per use case |
| 10 | Activity Diagrams | Process flows with decisions |
| 11 | Error Map | Error handling documentation |
| 12 | Risk Matrix | Technical risk assessment |
| 13 | Technical Decisions (ADR) | Architecture Decision Records |

All diagrams are generated in **Mermaid** format.

## After Documentation

The skill offers an **implementation bridge**:
- Generate a phased implementation plan
- Create project scaffold (directory structure + stubs)
- Generate test contracts from documentation
- Or all of the above

## Installation

Copy the `software-architect/` directory into your Claude Code skills folder:

```bash
# Clone the repo
git clone https://github.com/aburriyo/software-engineer-skill.git

# Copy to your Claude Code skills directory
cp -r software-engineer-skill/software-architect ~/.claude/skills/
```

## Usage

The skill activates automatically when you say things like:
- "Plan this app"
- "Document this project"
- "Generate engineering documentation"
- "I need the technical docs for this codebase"

Or invoke it directly by referencing the skill name.

## Key Features

- **Adaptive flow**: Asks questions if your idea is vague, generates directly if you have a detailed spec
- **Selective generation**: Choose which sections to generate
- **Auto-detection**: Detects if you have existing code (retrospective) or are starting fresh (prospective)
- **Cross-references**: Documents link to each other (e.g., sequence diagrams reference use cases)
- **Inference markers**: Clearly marks `[INFERRED]` assumptions and `[PENDING]` unknowns
- **Configurable output**: Default `docs/engineering/`, but you can specify any path

## Structure

```
software-architect/
  SKILL.md                          # Main orchestrator (lightweight)
  reference/
    prospective-flow.md             # New project planning flow
    retrospective-flow.md           # Existing project documentation flow
    sections-catalog.md             # Templates for all 13 sections
    implementation-bridge.md        # Plan + scaffold + tests generation
```

## Author

Created by **Bastian** ([@aburriyo](https://github.com/aburriyo))

## License

MIT License - see [LICENSE](LICENSE) for details.
