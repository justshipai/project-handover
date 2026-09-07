# Project handover

Leave the next AI session ready to pick up your work.

A reusable skill that maintains a concise `HANDOVER.md` in your project. It records what changed, why decisions were made, what was actually verified and where to start next.

Inspired by [Spotify's approach to shared context](https://portal.spotify.com/blog/introducing-xirp). Independent project; not affiliated with Spotify.

## What it does

- Saves the current goal, constraints and implementation state.
- Separates confirmed decisions from proposals and assumptions.
- Records checks that passed, failed or were not run.
- Preserves useful failed attempts and unresolved questions.
- Updates existing notes and removes obsolete information.
- When resuming, checks for changes since the handover was written.

It aims for roughly 300–600 words, with less for small tasks. It does not create a growing transcript or claim that untested work is complete.

## Install in Claude Code

Clone this repository into your personal skills directory:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/justshipai/project-handover.git ~/.claude/skills/project-handover
```

For a project-specific installation, use `.claude/skills/project-handover` inside that project instead.

## Use it

In Claude Code, after installing:

```text
/project-handover Wrap up this session and save a handover.
```

When returning:

```text
/project-handover Read the handover, check the current state and continue with the next step.
```

The skill is named `project-handover`, so its standalone Claude Code command is `/project-handover`, not `/handover`. See [Claude Code's skills documentation](https://code.claude.com/docs/en/skills).

In other tools that support skills, install the folder using that tool's supported method and ask it to use `project-handover`. The core instructions are plain Markdown and do not depend on a particular model or connector. Invocation syntax varies by tool.

## What to expect

The skill reuses an existing project handover, or creates `HANDOVER.md` in the project root. Review consequential decisions and verification claims before relying on them. Another tool needs access to the same project files to use the handover.

It runs within an active session. Closing an app does not trigger it, and installing it does not configure automatic loading in other tools. It does not commit, push or deploy your project just to save a handover.

## Files

- `SKILL.md` contains the workflow.
- `agents/openai.yaml` supplies interface metadata for supporting tools.
- `assets/icon.svg` supplies the skill icon.

The skill passed structural validation. Its usefulness across different models and projects still needs real-world testing.
