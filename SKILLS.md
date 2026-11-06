# AI-SDLC Skills Catalog

This document describes the skills available in the AI-SDLC repository, their capabilities, usage instructions, and expected outputs.

All skills are designed to be compatible with OpenAI Codex.

---

## 1. Refine Requirements

**Skill name:** `refine-requirements`

**Location:** `skills/refine-requirements/SKILL.md`

### Purpose

The `refine-requirements` skill helps transform vague, incomplete, or ambiguous feature and application requirements into clear, structured, and actionable requirements through an interactive Q&A session.

It acts as a requirements analyst, identifying gaps, challenging assumptions, and facilitating decisions before proceeding to solution design and implementation.

### Key Capabilities

- **Interactive Q&A:** Asks one clarifying question at a time.
- **Ambiguity Identification:** Identifies vague statements, missing information, and implicit assumptions.
- **Dependency Management:** Sequences questions based on dependencies between decisions.
- **Guided Answers:** Provides reasonable answer options with recommended defaults while allowing free-text responses.
- **Project Context Discovery:** Optionally inspects the current project directory for existing technical context.
- **Session Persistence:** Records the complete question-and-answer history, decisions, assumptions, and unresolved items.
- **Session Resumption:** Allows users to continue previously interrupted or terminated refinement sessions.
- **Early Termination:** Allows users to exit the Q&A session at any point using `exit-qna`.

### How to Invoke

Once installed, invoke the skill in Codex using:

```text
$refine-requirements
```

You can also provide the initial requirement directly:

```text
$refine-requirements Build an application that allows customers to track their orders.
```

Alternatively, use a natural-language instruction:

```text
Use the refine-requirements skill to refine the following feature:

Build an application that allows customers to track their orders.
```

### Project Context Discovery

By default, the skill can optionally inspect the current project directory to understand existing technical context.

For example:

```text
Use the refine-requirements skill to refine the order tracking feature.
Also inspect the current project for relevant architecture,
technology stack, APIs, and existing business rules.
```

Project inspection helps avoid asking questions that can already be answered using existing project information.

### Resuming a Session

Refinement sessions are persisted as timestamped Markdown files, allowing users to resume discussions across separate Codex sessions.

To resume a specific session, provide its file path:

```text
Resume the requirements refinement session from:

requirements/refinement-sessions/refinement-session-20261106-123000.md
```

To resume the latest session, ask:

```text
Resume my latest requirements refinement session.
```

The skill loads the previous Q&A history, reviews confirmed decisions and unresolved questions, and continues from where the discussion stopped.

### Ending a Session

At any point during the Q&A, enter:

```text
exit-qna
```

The skill terminates the session and saves the current progress, including unanswered questions and unresolved items.

A terminated session can be resumed later.

### Output Artifacts

The skill saves refinement sessions as timestamped Markdown files.

**Default output directory:**

```text
requirements/refinement-sessions/
```

**Example:**

```text
requirements/
└── refinement-sessions/
    ├── refinement-session-20261106-123000.md
    └── refinement-session-20261106-153000.md
```

Each session captures:

- Original requirement.
- Relevant project context, if inspected.
- Questions and available answer options.
- User-provided answers.
- Confirmed decisions.
- Identified assumptions.
- Unresolved questions.
- Refined requirement summary.
- Acceptance criteria and readiness assessment, where available.

The user can specify a different output location when starting a session.

### Detailed Documentation

Refer to the individual skill specification for its complete workflow, question-generation guidelines, dependency management, persistence rules, and session-resumption behavior.

[Refine Requirements - SKILL.md](skills/refine-requirements/SKILL.md)

---

## Future Skills

The following skills are planned as part of the broader AI-SDLC initiative:

| Skill | Purpose |
|---|---|
| Requirements Validation | Validate requirements for completeness, consistency, and testability. |
| Architecture Design | Develop high-level and low-level architecture specifications. |
| Implementation Planning | Convert approved specifications into actionable implementation tasks. |
| AI-Assisted Implementation | Guide coding agents using approved requirements and design context. |
| Implementation Verification | Verify implementation against requirements and design specifications. |
| Governance & Traceability | Maintain relationships between requirements, decisions, designs, and implementation artifacts. |

Additional skills will be documented here as they become available.