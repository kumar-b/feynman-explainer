# feynman-explainer

A Claude Code skill plugin that explains any concept the way Richard Feynman would — from first principles, with vivid analogies, honest acknowledgment of where things get weird, and a real simulated audience check before delivering the final answer.

## What It Does

Trigger the skill with phrases like **"explain like Feynman"**, **"ELI5"**, **"explain simply"**, or **"I don't understand X"** — and Claude will:

1. Ask which audience level you want: 5-year-old (default), teenager, or adult with no background
2. Strip the concept to its single essential core and identify the most common misconception
3. Build a structured explanation: motivation → surface misconception → curiosity hook → build from zero → analogy → honest bump → deeper layer → so what
4. Spawn a real subagent (context-isolated, cold-read) that reacts as that audience would — returning up to 3 concrete gaps
5. Revise the explanation from scratch to address every gap

The Audience Agent in Step 4 is a genuine subagent with no knowledge of the topic or how the explanation was built. Its confusion is real, not simulated.

## Installation

### As a Claude Code Plugin

```bash
claude --plugin-dir ./feynman-explainer
```

Or add it permanently in your Claude Code settings:

```json
{
  "plugins": ["/path/to/feynman-explainer"]
}
```

### As a Standalone Skill

Copy `skills/feynman-explainer/SKILL.md` into your project's `.claude/skills/feynman-explainer/` directory.

## Usage

Once installed, trigger the skill naturally in conversation:

```
explain like Feynman: how does HTTPS work?
ELI5 entropy
I don't understand why recursion works
explain gradient descent simply
```

Claude will ask for the audience level (or default to 5-year-old), then deliver a complete Feynman-style explanation with an audience-agent feedback loop and a revised final version.

## Skill Design

The skill is backed by research across cognitive science, learning science, and expert science communicators (Feynman, Grant Sanderson, Derek Muller, Andrej Karpathy, Steven Pinker). Key design decisions:

- **Misconception-first** — surfaces the wrong model before correcting it (Muller 2008: clear explanations delivered to misconception-holders produce no learning without prior misconception activation)
- **Motivation signal upfront** — Sanderson: "motivation is the primary limiting factor, ahead of explanation quality itself"
- **Structurally accurate analogies** — must hold when pushed one level deeper; surface-only analogies create new misconceptions
- **Honest bump** — every concept has a place where it gets genuinely strange; naming it builds trust
- **Real audience feedback** — the Audience Agent is context-isolated so its gaps are genuine, not performed

See [`resources.md`](resources.md) for the full research base behind v4.0.0.

## Repository Structure

```
feynman-explainer/
├── .claude-plugin/
│   └── plugin.json              # Plugin registration metadata
├── skills/
│   └── feynman-explainer/
│       └── SKILL.md             # Full skill definition
├── resources.md                 # Research backing the skill design
└── CLAUDE.md                    # Guidance for Claude Code in this repo
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT — see [LICENSE](LICENSE).

## Author

Kumar Biswaranjan
