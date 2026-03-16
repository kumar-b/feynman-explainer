# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A Claude skill plugin that teaches Claude to explain concepts in Richard Feynman's style. There is no build system, dependencies, or runnable code — the entire implementation is the instruction set in `skills/feynman-explainer/SKILL.md`.

## Repository Structure

- `.claude-plugin/plugin.json` — Plugin registration metadata (name, description)
- `skills/feynman-explainer/SKILL.md` — The full skill definition: trigger conditions, explanation methodology, tone guidelines, and calibration examples

## How the Skill Works

The skill is triggered by phrases like "explain like Feynman", "ELI5", "explain simply", etc. It follows a 5-step methodology:

1. **Ask about audience** — 5-year-old (default), teenager, or adult with no background
2. **Find the core** — one essential concept, one common misconception, one everyday analogy
3. **Build the explanation** — Hook → Build from zero → Analogy → Honest bump → Deeper layer (non-child only) → So what
4. **Audience Agent feedback** — Claude spawns a true subagent (via the `Agent` tool) passing only the finished explanation text and the audience persona description. The subagent has no context about the topic or how the explanation was constructed, so its confusion is genuine, not simulated. It returns at most 3 concrete gaps.
5. **Revised explanation** — Claude rewrites the weak parts; the revision must be complete and self-contained, not a patch

The Audience Agent is a real subagent — context isolation is the point. Do not collapse it back into a role-play within the same context. The revised explanation must re-check the Step 3 structure.

The "honest bump" (acknowledging where a concept gets genuinely strange or unknown) is load-bearing — don't remove or soften it.

## Editing Guidelines

When modifying `SKILL.md`, preserve the frontmatter block (`---` delimited), which contains the trigger description that determines when Claude activates this skill. Changes to the trigger phrases in the frontmatter directly affect skill invocation.
