# xlabs-agent-skills

[中文版](README.zh-CN.md)

<p align="center">
  <strong>Skills and agents for AI coding assistants.</strong><br>
  Things we built to make our daily work smoother — here to share.
</p>

---

We use AI coding agents in our daily development, and over time we've built up
a set of skills, agent configurations, and conventions that help things run
more reliably. This repo is where we keep them.

It's not a framework. No grand theory. Just patterns we've found useful, written
down so others can use them too.

## What's different

We try to keep things simple:

- **Each skill is one directory** with a `SKILL.md` that includes spec,
  usage, and a self-check section — all in one file.
- **Agents compose skills** instead of embedding logic directly. Makes them
  easier to test and reuse.
- **Everything runs on `bash`** — no runtime dependencies beyond what's in
  a standard terminal.
- **CI enforces quality** — markdownlint on every push.

## What's inside

```text
xlabs-agent-skills/
├── skills/                      # Individual capabilities
│   └── <name>/
│       └── SKILL.md             #   What it does, how to use it, how to check it
│
├── agents/                      # Workflows that combine skills
│   └── <name>/
│       └── AGENT.md             #   Purpose, flow, and verification
│
├── templates/                   # Starting points for new skills and agents
│   ├── skill-template/
│   └── agent-template/
│
├── docs/                        # Architecture notes and best practices
└── scripts/                     # Maintenance and validation scripts
```

## Quick start

```bash
git clone https://github.com/xlabs-club/xlabs-agent-skills.git
cd xlabs-agent-skills

# Create a skill from the template
cp -r templates/skill-template skills/my-skill
# Edit skills/my-skill/SKILL.md to implement your skill
# Include a self-check section — one command that proves it works
```

## Contributing

If you've built something useful, we'd love to include it. Three things we ask:

- Include a self-check — one command that proves it works.
- Keep it focused — one skill, one job.
- Use it yourself before submitting.

PRs welcome. See [AGENTS.md](AGENTS.md) for the full conventions.
