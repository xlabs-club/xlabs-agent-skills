# Best Practices

## Writing a skill

- **SKILL.md is the API.** Read it before implementing. Write it before coding.
- **One self-check command.** SKILL.md must include a command the reader can
  run to verify the skill works. Exit 0 on success, non-zero on failure.
- **No silent failures.** Every error path prints to stderr.
- **Prefer `#!/usr/bin/env bash`.** Portable, predictable, everywhere.

## Writing an agent

- **An agent is a recipe, not a runtime.** Document the flow, don't build a framework.
- **Fail early.** If preconditions aren't met, say so immediately.

## Code review checklist

- [ ] Does this need to exist? (YAGNI check)
- [ ] Could stdlib or an existing tool do it?
- [ ] Is there a self-check?
- [ ] Are failure modes documented?
- [ ] Is it the simplest thing that works?
