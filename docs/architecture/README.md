# Architecture

## Design principles

1. **Skills are the atom** — everything composes from skills. An agent is a
   directed acyclic graph of skill invocations.

2. **No hidden state** — every skill invocation is self-contained. The agent
   passes context explicitly.

3. **Shell over SDK** — `bash` is the universal runtime. A skill that works in
   a terminal works in CI, in a hook, or in an agent. No framework lock-in.

4. **Self-check is glue** — every skill includes a one-command verification
   in its `SKILL.md`. If it passes, the skill works. No ambiguity.

## Skill invocation model

```text
User/Agent → Skill("name", args) → shell/cmd → output
                ↑
            SKILL.md (spec + implementation)
```

## Safety

- Skills never access the network unless explicitly documented.
- Skills never modify files outside the project root.
- Destructive operations require explicit confirmation.
- Every skill has a documented failure mode.
