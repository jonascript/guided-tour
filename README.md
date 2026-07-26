# guided-tour

A [Claude Code](https://claude.com/claude-code) skill that turns Claude into a **live,
interactive tour guide for any codebase** — a hands-on tutor that walks you through how the
code actually works, one digestible concept at a time, pausing at real checkpoints so you
can ask questions, go deeper, or change direction at any moment.

This is the conversational counterpart to walkthrough-generator skills: instead of handing
you a static document or HTML file, the tour **is** the session.

## What it does

- **Grounds every claim in real code.** Every explanation cites `file:line` references from
  files Claude actually read — no invented snippets, no fuzzy paraphrasing. When unsure, it
  goes and looks.
- **Hands you the wheel — genuinely.** Each stop ends with a real checkpoint offering
  concrete next directions. Your questions aren't interruptions to the plan; they *become*
  the plan, and the tour resumes when you're ready.
- **Calibrates depth as it goes.** Starts at competent-engineer-new-to-this-repo altitude,
  then adjusts from your questions — unpacking fundamentals on request, speeding up when
  you're ahead of it.
- **Draws when a picture beats prose.** ASCII sketches, Mermaid, or richer diagram tools
  depending on what your client renders.
- **Scales to large codebases** by refusing to "cover" them: it fans out parallel explore
  agents to map the terrain, then tours the ~20% that carries the mental model. A 200K-line
  codebase is a focused sitting, not a slog.

## Install

Copy the skill into your global skills directory:

```bash
git clone --depth 1 https://github.com/jonascript/guided-tour /tmp/guided-tour && mkdir -p ~/.claude/skills && cp -R /tmp/guided-tour/skills/guided-tour ~/.claude/skills/
```

Or install with [skills](https://github.com/obra/skills):

```bash
npx skills add https://github.com/jonascript/guided-tour --skill guided-tour
```

New skills are picked up at session start — open a fresh Claude Code session after
installing.

## Use

Invoke it directly:

```
/guided-tour path/to/repo
```

Or just ask naturally in any repo:

- "give me a guided tour of this codebase"
- "walk me through how authentication works — and let me ask questions"
- "I'm new to this project, where do I start?"
- "onboard me to this repo"

The tour proposes a short itinerary, gets your nod, and starts. Interrupt it whenever you
like — that's the point.

## Tips from real tours

- **Articulate your model back.** Explaining a stop in your own words and asking Claude to
  grade it point-by-point is the fastest way to find the gaps.
- **Chase tangents.** "Could this pattern apply to my project at work?" produces some of the
  best sessions — the skill follows you there and back.
- **Propose designs.** Try "what if it worked like X instead?" and let the tour review your
  idea against the real code's constraints.

## License

MIT
