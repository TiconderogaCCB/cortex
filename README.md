# cortex

**A structured memory system for AI-assisted development.**

Give your AI a persistent, queryable memory that travels with you. Allowing your work and development to compound over time. An element that you can connect and disconnect from any AI assistant, project, platform, or employer.

---

## What This Is

As my knowledge about the tools and AI grew, naturally so did the complexity of what we were building. I kept wanting some type of persistent memory to help expedite new context window understanding of the status quo, and the journey that got us there. I felt I was hitting a wall without a true assistant that acted as if it was there at every step. So we built one out through trial and error, landing on this pretty effective method of maintaining a sustained working relationship with milestones, contributions, achievements, pitfalls, etc.

It's a way to track my own personal growth with the technology, and to record the relationship over time between AI and the user. When you work with AI on real world builds every session starts from zero. The AI doesn't remember the 6 hours you spent developing the perfect schema and the architectural decisions you made for good reasons, or the convention you've established over months of real work.

The cortex pattern is a structured directory of plain Markdown files that gives an AI persistent, semantic memory across sessions. It's organized by knowledge type, queryable by meaning rather than keyword, and designed to travel with the person, not the project.

This repo contains the framework, the structure, the tooling, and the patterns. The content is yours to write.

---

## Structure

```text
cortex/
├── tkb/                    # Technical Knowledge Base
│   ├── semantic.md         # Naming conventions, data patterns, type decisions
│   ├── procedural.md       # Step-by-step workflows that have been proven to work
│   ├── decisions.md        # Architectural decisions with rationale (ADR format)
│   └── pitfalls.md         # Known bugs, gotchas, and traps
├── ckb/                    # Cognitive Knowledge Base
│   ├── journal.md          # Running session journal
│   └── sessions/           # Dated session logs
└── peb/                    # Personal Experience Base (optional - own layer)
    ├── profile.md          # Who you are and how you think (public shape)
    ├── skills.md           # Demonstrated skills with context and evidence
    ├── journey.md          # The full story - how you got here
    ├── values.md           # Values expressed through choices
    ├── history.md          # Significant decisions and what they revealed
    └── private/            # Owner-only, never indexed (gitignored)
```

---

## Why Three Layers

**TKB (Technical):** What the AI needs to be useful in the work. Project-specific, written to be handed off. If the project were handed to a new engineer with an AI assistant, the TKB gives the AI everything it needs to be helpful from day one.

**CKB (Cognitive):** The human side of the work. How you got here, what you tried, what failed, how the thinking evolved. Not useful to an AI doing technical tasks - useful to an AI working with *you specifically* on understanding and strategy.

**PEB (Personal):** Portable personal record. Not a resume, not a profile page. Structured personal history queryable by an AI the same way the TKB is queryable for technical context. Travels with the person across any job, project, or platform.

These layers are independent. You can run just TKB. You can add CKB later. PEB is optional and entirely personal.

---

## The Bootstrap Pattern

The cortex is only as useful as what loads at session start. The bootstrap is a curated summary of the highest-signal content - recent session logs, open decisions, active pitfalls - delivered in a format the AI can use immediately.

```text
Session start → bootstrap → AI has context → work begins informed
```

The bootstrap is not the entire cortex. It's the right 5-10% for right now.

---

## Querying

Cortex files are indexed as embeddings. Queries are semantic:

```text
"What's the established pattern for handling X?"
"What decisions have we made about Y?"
"What pitfalls are associated with Z?"
```

Returns the specific entries that matter, not everything that mentions the topic.

The MCP server handles indexing, querying, and session logging. See [setup](#setup).

---

## Setup

> *Coming: MCP server setup, embedding configuration, and cortex bootstrap tooling.*

Manual bootstrap (no MCP server):

1. Create the directory structure above
2. At session start, paste the contents of your highest-priority files into the AI context
3. At session end, update your journal and pitfalls with anything new

This works. It's manual. The MCP layer automates it.

---

## Writing Conventions

The cortex is worth maintaining only if the entries are worth reading. A few principles that matter more than any template:

**Write with evidence, not aspiration.** "I am good at X" is noise. "We decided against X because of Y, and here's what that cost us" is signal.

**Decisions require rationale.** Not just "we chose this" - "we chose this over these alternatives, because of these constraints, and here's what would have to change for us to revisit it."

**Pitfalls require reproduction steps.** A pitfall without a specific trigger is just vague anxiety. "This fails when Z happens" is useful. "Be careful with X" is not.

**Session logs are the compounding asset.** The individual log doesn't matter much. The pattern across 50 logs is irreplaceable. Write them consistently even when the session feels uneventful.

---

## The Portability Principle

The cortex belongs to its author, not to any project or employer.

The TKB for a specific project is project-specific and stays with the project. But the CKB and PEB travel with the person. When you change jobs, take on a new project, or start fresh, your cognitive base and personal layer come with you.

Key management for sensitive personal content (PEB) should live in a portable zero-knowledge vault (e.g. Bitwarden), not tied to any project's infrastructure.

---

## What This Isn't

- Not a RAG system for your company's documentation
- Not a replacement for good code comments
- Not a prompt engineering toolkit
- Not a product you deploy for a team

It's a personal infrastructure pattern. One person, one cortex, maintained over time. The value is cumulative and individual.

---

## Contributing

The framework is open. The conventions are documented. The structure is intentional.

If you have improvements to the framework structure, tooling, or conventions, open an issue or PR. The content is yours; the pattern benefits from being stress-tested by more practitioners.

---

## License

MIT for code and framework structure.
CC BY 4.0 for documentation and written conventions.

You own your cortex content entirely. This license covers the framework itself.

---

## Author

> *Not a coder or developer by trade, but I've transformed a bit over the last couple of years into a new type of systems architect at night, and construction professional by day. I've been in the commercial construction industry for over a decade. About two years ago, after listening to a Bill Gates interview, I made it a personal goal to learn and absorb as many elements of AI and other technological developments as possible in an effort to understand and play a role in that emerging field. Knowing my limitations and lack of traditional technical training, I've been working on effective ways to document my individual contributions to the development of software, and other projects I'm passionate about. This repo is a reflection of that work - a practitioner's attempt to make the collaboration compound rather than reset.*
