# AI-SDLC

**An open-source collection of AI skills for building an AI-driven Software Development Lifecycle (SDLC).**

AI-SDLC aims to bring structure, consistency, and governance to AI-assisted software development through a collection of reusable, specialized skills.

The goal is to move beyond ad hoc AI prompting towards a structured development lifecycle in which AI agents assist with requirements discovery, analysis, design, implementation, and verification.

## Vision

Traditional software development follows a structured lifecycle, with well-defined activities, artifacts, and checkpoints.

As AI coding agents become increasingly capable, there is an opportunity to apply the same discipline to AI-assisted software development.

AI-SDLC explores this approach by providing specialized skills that guide AI agents through individual SDLC activities.

The broader vision is to establish a workflow where:

- Requirements are systematically refined before design and implementation.
- Design decisions are based on clear, validated requirements.
- Implementation is guided by approved specifications.
- Code is verified against requirements and design decisions.
- Decisions, assumptions, and artifacts remain traceable throughout the lifecycle.

## Skills

All skills in this repository are designed to be compatible with **OpenAI Codex**.

The repository currently includes the following skill:

### Skills Catalog

| Skill | Description | Documentation |
|---|---|---|
| `refine-requirements` | Refines vague or incomplete feature and application requirements through interactive, adaptive Q&A. Identifies ambiguities, assumptions, dependencies, and missing information. | [Usage & Documentation](skills/refine-requirements/SKILL.md) |


### Refine Requirements

The `refine-requirements` skill helps turn initial feature or application ideas into structured requirements through an interactive Q&A session.

**How it works:**
- Analyzes the initial requirement to identify ambiguities, gaps, and implicit assumptions.
- Optionally inspects the current project directory for project-specific technical context.
- Conducts an adaptive Q&A session, asking one clarifying question at a time.
- Presents reasonable answer options with recommended defaults.
- Maintains question dependencies and adapts subsequent questions based on previous answers.
- Allows the user to terminate the session at any point using `exit-qna`.

**How to invoke:**

Once installed, invoke the skill in Codex by referring to its name:

```text
$refine-requirements Build an application that allows customers to track their orders
```

You can also invoke it using a natural-language instruction, for example:

```text
Use the refine-requirements skill to refine the following feature:

Build an application that allows customers to track their orders.
```

You can optionally ask the skill to inspect the current project directory for additional technical context.

**Output:**

The complete Q&A history, including questions, answers, confirmed decisions, assumptions, and unresolved items, is saved as a timestamped Markdown file under:

```text
requirements/refinement-sessions/
```

Example:

```text
requirements/
└── refinement-sessions/
    └── refinement-session-20261106-123000.md
```

See [Skill Documentation](skills/refine-requirements/SKILL.md) for detailed behavior and usage instructions.

### Installation

See [How to Install](#how-to-install) for instructions on installing individual skills.

## Planned Capabilities

The following capabilities represent the broader direction of the project and are subject to change.

| Capability | Purpose |
|---|---|
| Requirements Refinement | Discover and clarify business and functional requirements. |
| Requirements Validation | Identify inconsistencies, ambiguities, and gaps. |
| Architecture Design | Develop high-level and low-level design specifications. |
| Implementation Planning | Translate approved specifications into implementation tasks. |
| AI-Assisted Implementation | Guide coding agents using approved requirements and design context. |
| Verification | Validate implementation against requirements and acceptance criteria. |
| Governance & Traceability | Maintain decision history, approvals, assumptions, and artifact relationships. |

## Repository Structure

```text
ai-sdlc/
├── skills/
│   └── refine-requirements/
│       └── SKILL.md
├── README.md
└── LICENSE
```

Additional skills and supporting resources will be introduced as the project evolves.

## How to Install

Skills are maintained in the `skills/` directory.

You can install an individual skill by copying its directory into one of the following Codex skill locations.

**Option 1: Project-level installation**

```text
<project-root>/.agents/skills/
```

For example:

```text
<project-root>/.agents/skills/refine-requirements/SKILL.md
```

This makes the skill available within the corresponding project.

**Option 2: User-level installation**

```text
~/.agents/skills/refine-requirements/SKILL.md
```

This makes the skill available across your Codex projects.

After installation, invoke the skill by its name:

```text
refine-requirements
```

Refer to the individual skill's documentation for its usage and behavior.

## Contributing

Contributions, suggestions, and discussions are welcome.

Areas of interest include:

- New SDLC skills.
- Improvements to existing skills.
- Better requirements analysis and validation techniques.
- Agent workflows and orchestration.
- Governance, traceability, and verification approaches.
- Examples and practical usage scenarios.

The intention is to build this as an evolving, reusable foundation for structured AI-assisted software development.

## Project Status

**Early development / Experimental**

The repository is evolving. Skills and workflows may change as the overall AI-SDLC approach develops.

## License

See [LICENSE](LICENSE) for licensing information.