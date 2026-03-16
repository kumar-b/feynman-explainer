# Contributing

Contributions are welcome — improvements to the explanation methodology, tone guidelines, calibration examples, or research backing.

## What's Worth Changing

- **`SKILL.md`** — the core skill definition. Changes here directly affect how Claude explains things.
- **`resources.md`** — the research base. If you find better sources or want to add a section, open a PR with the citation.

## What to Keep

- The **honest bump** — don't soften or remove it. It's load-bearing for trust.
- The **Audience Agent as a real subagent** — don't collapse it into a role-play within the same context. Context isolation is the point.
- The **misconception-first structure** — surface the wrong model before correcting it. This is backed by Muller (2008) and is not optional.

## How to Contribute

1. Fork the repo
2. Create a branch: `git checkout -b my-improvement`
3. Make your changes
4. Test the skill by invoking it in Claude Code with a few different topics and audiences
5. Open a pull request with a clear description of what changed and why

## Versioning

This skill uses semantic versioning in `plugin.json`. When opening a PR:

- Patch bump (`4.0.x`) — typo fixes, clarifications that don't change behavior
- Minor bump (`4.x.0`) — new calibration examples, tone adjustments, research additions
- Major bump (`x.0.0`) — structural changes to the 5-step methodology
