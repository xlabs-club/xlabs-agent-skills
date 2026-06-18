# xlabs AI Agents

> Skills and agents we use in our daily development — shared in case they're
> useful to you too.

## Identity

This is where we keep our AI coding assistant skills and agents. Everything
here is what we actually use. No demos, no filler.

## Philosophy

An agent is only as good as its constraints:

1. **Single responsibility** — one agent, one job. Compose, don't monolith.
2. **Verifiable output** — produces something you can check.
3. **Fail fast** — impossible request → say no clearly.
4. **Self-documenting** — `AGENT.md` is the spec, the code, and the help text.

## Conventions

- **Language**: docs and comments in Chinese, identifiers in English
- **Tone**: calm and pragmatic. No hype, no marketing. If it sounds like a
  pitch, rewrite it.
- **Skills** go in `skills/<name>/SKILL.md`
- **Agents** go in `agents/<name>/AGENT.md`
- Entry file is the source of truth — no separate docs to rot
- No dead code. Not used → deleted.
- Self-check is part of the entry file. No separate test harness.
- Prefer stdlib, zero-dependency. Every dependency is a liability.
- Shell: `#!/usr/bin/env bash` — runs everywhere
- Configuration over code. Convention over configuration.

## What's different

- **Skills-first.** Agents don't contain logic — they compose skills. Every
  capability is independently testable and reusable.
- **Shell runtime.** `bash` is the only dependency. No venv, no toolchain.
- **Self-check mandatory.** Every skill/agent ships with a one-command
  verification. CI enforces it.

## Quality bar

- A skill that errors in CI will be removed.
- No self-check → not merged.
- Duplicate purpose must justify why it's distinct.
- Every agent produces verifiable output. No hand-waving.

## Catalog

### Skills (`skills/`)

The atomic unit — small, focused capabilities.

| Skill | What it does |
|-------|-------------|
| *(growing — see [skills/](skills/))* | |

### Agents (`agents/`)

Workflows that compose skills.

| Agent | What it does |
|-------|-------------|
| *(growing — see [agents/](agents/))* | |

## Creating a new skill

```bash
cp -r templates/skill-template skills/<name>
# Edit SKILL.md — spec, usage, self-check
```

## Creating a new agent

```bash
cp -r templates/agent-template agents/<name>
# Edit AGENT.md — spec, flow, verification
```

## Rules

- YAGNI. Don't add what you won't use this week.
- Don't duplicate — extend.
- One sentence can't describe it → it does too much.
