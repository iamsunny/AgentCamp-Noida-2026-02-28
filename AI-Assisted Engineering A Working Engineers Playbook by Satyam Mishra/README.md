# AI-Assisted Engineering: A Working Engineer's Playbook

**Speaker:** [Satyam Mishra](https://www.linkedin.com/in/satyamml)
**Duration:** 2:00 PM – 2:30 PM IST

## Key takeaways

- **Specs are your highest-leverage artifact** — 10 minutes writing a 6-component spec saves 2+ hours of AI back-and-forth
- **Anti-requirements prevent the most common AI mistakes** — explicitly stating what NOT to do is as important as stating what to do
- **Review adversarially, not optimistically** — trace one real input manually; AI-generated code fails at edge cases and failure modes
- **CLAUDE.md / AGENTS.md loads context automatically** — no need to re-explain your stack and conventions every session
- **Slash commands make prompts reusable** — write the prompt once, invoke with `/command-name` for any repeated task
- **Parallel worktrees = parallel AI sessions** — run two branches simultaneously without conflicts or context switching

## About this session

AI coding tools get you 70% of the way there fast. The code runs, the happy path works — but production requires the other 30%. This talk covers two engineering disciplines that bridge that gap: spec-driven development and adversarial review, plus a repeatable toolchain to make both second nature.

> *Speed without structure just means you ship mistakes faster.*

## Key concepts

### Skill 1 — Spec-Driven Development

Your spec is your highest-leverage artifact. A 10-minute spec saves 2 hours of iteration.

A great spec has six components:

| # | Component | What it means |
|---|-----------|---------------|
| 01 | **Context** | Tech stack, relevant files, and *why* the feature exists |
| 02 | **Requirements + Edge Cases** | Not just the happy path — what happens with empty input, wrong language, etc. |
| 03 | **Non-functional Targets** | Numbers, not vibes — "response under 2s at P95" not "it should be fast" |
| 04 | **Examples** | Actual input/output pairs — the AI performs dramatically better with these |
| 05 | **Anti-requirements** | What NOT to do — prevents the most common AI mistakes |
| 06 | **Definition of Done** | Tests that must pass, what production output looks like |

### Skill 2 — Adversarial Review

Don't review to confirm it works. Review to find where it's wrong.

The **5-point review checklist:**

1. **Logic** — Trace one real input through the code manually
2. **Edge Cases** — Empty query? Wrong language? Oversized input?
3. **Failure Handling** — What if the DB is slow? API times out? Zero results?
4. **Dependencies** — What packages were added? Are they needed? Maintained?
5. **Consistency** — Does this match how the rest of your system works?

### The Toolchain — Making It Repeatable

| Tool | Purpose |
|------|---------|
| **Project config file** (`CLAUDE.md` / `.cursor-rules` / `AGENTS.md`) | Every AI session starts with your stack, conventions, and constraints already loaded |
| **Slash commands** (`.claude/commands/*.md`) | Reusable prompt templates — write once, invoke with `/command-name` |
| **Skills folders** | Bundles of instructions + scripts that auto-activate by context (e.g. `api-reviewer`, `deploy-checker`) |
| **Parallel worktrees** | Multiple AI sessions on separate branches simultaneously — no conflicts |

**Bonus:** Playwright MCP gives your AI coding tool real browser eyes — open, screenshot, check console errors, report back. One line to set up.

## Real-world example from the talk

A RAG pipeline built for HR policy docs worked perfectly in happy-path testing, then failed in production because:
- Employees used abbreviations, shorthand, and mixed Hindi/English
- The embedding model wasn't trained for this
- Wrong chunks were returned consistently

The AI had no idea how real employees search. The spec would have caught it.

## About the speaker

**[Satyam Mishra](https://www.linkedin.com/in/satyamml)** — AI Engineer at HROne, architecting conversational AI systems including employee self-service agents, policy automation, OCR systems, and workflow orchestration. Specializes in production-grade RAG systems, vector databases, and multi-agent architectures using LangGraph, FastAPI, and modern LLM technologies.

## Further reading & tools

| Resource | What it is |
|----------|------------|
| [Claude Code](https://claude.ai/code) | Anthropic's CLI for AI-assisted engineering — the primary tool demoed in this session |
| [Cursor](https://cursor.com/) | AI-first code editor with `.cursor-rules` project config support |
| [Playwright MCP](https://github.com/microsoft/playwright-mcp) | Give your AI coding tool real browser eyes — one line to set up |
| [git worktree](https://git-scm.com/docs/git-worktree) | Built-in Git feature for parallel branches without stashing or switching |
| [OWASP Top 10](https://owasp.org/www-project-top-ten/) | The adversarial review checklist for security — pairs with the 5-point review |
| [Conventional Commits](https://www.conventionalcommits.org/) | Spec for structured commit messages — useful to encode in your project config file |

## Slides

[The AI Is Fast. But You Are The Engineer.pdf](The%20AI%20Is%20Fast.%20But%20You%20Are%20The%20Egineer.pdf)

## Five things you can do this week

1. **Create a project config file** — `CLAUDE.md` / `.cursor-rules` / `AGENTS.md` *(30 min)*
2. **Write one proper spec** — all six components before your next AI session *(15 min)*
3. **Run the 5-item review checklist** — on your last AI-generated PR *(20 min)*
4. **Create one slash command** — for a task you repeat weekly *(5 min)*
5. **Try parallel worktrees** — two terminals, two branches, two AI sessions *(10 min)*
