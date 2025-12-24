# xlabs-agent-skills

[English](README.md)

<p align="center">
  <strong>给 AI 编码助手用的 skills 和 agents。</strong><br>
  我们在日常开发中积累的一些东西，分享出来。
</p>

---

我们每天都在用 AI 编码助手，用得久了，慢慢攒了一些 skills、agent 配置和约定，
让工作流程更稳定一些。这个仓库就是放它们的地方。

不是什么框架，也没有宏大理论。就是一些我们觉得好用的模式，记录下来，希望对别人也有用。

## 我们的一些做法

尽量保持简单：

- **每个 skill 一个目录**，里面有 `SKILL.md`，包含规范、用法和自检 —— 一个文件搞定。
- **Agent 组合 skill**，不把逻辑塞在一起。这样更容易测试和复用。
- **全部跑在 `bash` 上** — 标准终端就行，不需要额外装什么运行时。
- **CI 兜底质量** — 每次 push 跑 markdownlint。

## 目录结构

```text
xlabs-agent-skills/
├── skills/                      # 单个能力
│   └── <name>/
│       └── SKILL.md             #   做什么、怎么用、怎么验证
│
├── agents/                      # 组合 skills 形成工作流
│   └── <name>/
│       └── AGENT.md             #   目的、流程、验证方式
│
├── templates/                   # 新建 skill / agent 的起点
│   ├── skill-template/
│   └── agent-template/
│
├── docs/                        # 架构笔记和最佳实践
└── scripts/                     # 维护和验证脚本
```

## 快速开始

```bash
git clone https://github.com/xlabs-club/xlabs-agent-skills.git
cd xlabs-agent-skills

# 从模板创建一个 skill
cp -r templates/skill-template skills/my-skill
# 编辑 skills/my-skill/SKILL.md 实现你的 skill
# 在 SKILL.md 里加上自检 — 一条命令证明它能用
```

## 参与贡献

如果你也做了有用的东西，欢迎放进来。就三条：

- 带一个自检 — 一条命令证明它能用。
- 保持专注 — 一个 skill 只做一件事。
- 先自己用用再提交。

PR 欢迎。完整的约定和质量标准见 [AGENTS.md](AGENTS.md)。
