# The K9Core Pattern: How We Gave an AI a Persistent Memory That Goes Wherever We Go

*By Caleb Bissett — Published 2026-03-29*

---

I'm not a developer by trade. I'm a construction professional who spent the last two years learning to build real software with AI as a collaborator. And somewhere in that process, I ran into a problem nobody seemed to be talking about directly.

Every session started from zero.

The AI would make the same mistakes we'd already fixed. It would propose patterns we'd already rejected. It had no memory of why we built things the way we built them. I kept wanting some type of persistent memory to help expedite new context window understanding of the status quo, and the journey that got us there. I felt I was hitting a wall without a true assistant that acted as if it was there at every step.

The official answer is "put everything in the prompt." Which is fine until your project has eighteen months of accumulated decisions, a dozen discovered bugs, and patterns that only make sense in context.

So we built one out through trial and error. We call it K9Core.

---

## What K9Core Is

K9Core is a directory of plain Markdown files. No framework. No database required. No magic. The structure is what makes it useful.

It has two main layers:

**The Technical Knowledge Base (TKB)** holds what the AI needs to be useful:

- Architectural decisions with rationale, not just "what we chose" but "why, what we considered, and what would have to change for us to revisit it"
- Known pitfalls, bugs and gotchas that have already cost time
- Naming conventions and type patterns
- Step-by-step workflows that have been proven to work

**The Cognitive Knowledge Base (CKB)** holds the human side of the work:

- A running journal of each session - what changed, what was attempted, what was learned
- Session logs in a consistent format: date, decisions made, what was tried and failed, open questions
- Pattern observations - things noticed about how the work evolves over time

The AI reads a bootstrap summary at the start of each session - a curated digest of the highest-signal content across both layers. It takes about fifteen seconds and changes everything about the quality of the session that follows.

---

## The Part That Surprised Me

I expected the technical layer to be useful. What I didn't expect was how much the cognitive layer would matter.

Writing a session log forces a kind of meta-clarity that doesn't happen otherwise. "What actually happened today? What did we learn? What's still open?" That discipline - done consistently - creates a record of reasoning, not just code. And that record is genuinely useful for the AI to hold.

There's a difference between an AI that knows your architecture and an AI that knows your architecture *and* knows you had a rough session two weeks ago debugging a subtle race condition, and that as a result you now check X before touching Y. The second AI is closer to a collaborator. The first is just a fast search engine over your codebase.

It's also a way to track my own personal growth with the technology, and to record the relationship over time between AI and the user. That turned out to matter more than I expected.

---

## The Vector Layer

The Markdown files are human-readable and AI-queryable. A background indexing process embeds all K9Core content into vectors - so rather than loading everything at session start, semantic search returns the specific entries that matter right now. As K9Core grows, this becomes the difference between a useful tool and an overwhelming one.

---

## What We're Building Toward

The next layer is personal: a structured record of demonstrated skills, values expressed through choices, and personal history - written for AI query the same way the TKB is written for technical query.

Not a resume. Not a profile page. A record of judgment demonstrated in context, organized so an AI can accurately answer: "What are this person's actual strengths?" or "What has this person done when things got hard?"

The idea is that knowledge - technical, cognitive, personal - compounds when it's structured. K9Core is an infrastructure play on your own accumulated wisdom.

---

## The Anti-Template Warning

K9Core is not a template you install. It's a discipline you maintain. The value comes from accumulated specificity - the pitfall that's relevant to *your* codebase, the decision that made sense in *your* context, the session log that captures why *you* chose what you chose.

A K9Core you copy from someone else is not your K9Core. Start with structure and fill it with your own content. Write badly at first. The discipline matters more than the quality of any individual entry.

---

## Why I'm Writing About This

Not because I've solved anything. Because I spent a year building something in private that's worth describing publicly, and describing it is how you find out if it's as useful as you think.

If you're working with AI on anything real - a product, a codebase, a research project - and you're not maintaining some version of a persistent memory layer, you're starting over every session. The K9Core pattern is one answer to that. There are others. The question is worth taking seriously.

The framework is open source: [github.com/TiconderogaCCB/K9Core](https://github.com/TiconderogaCCB/K9Core)

---

*More on the technical architecture and the Personal Experience Base in a follow-up piece.*
