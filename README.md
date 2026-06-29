# Silence

Silence is a skill for Codex and Claude Code that enables quiet, final-only work. It tells the assistant to avoid interim narration and return only verified final results, while still allowing required approval prompts, blocker questions, tool failures, and safety constraints. Once invoked, it stays active across intermediate continuations and resumed goal work until the user cancels it or the goal is fully achieved.

## Install

In Codex, run:

```text
$skill-installer https://github.com/jake-w-liu/silence/tree/main/silence
```

Restart Codex after installation so the new skill is discovered.

## Install (Claude Code)

In Claude Code, run:

```text
claude plugin marketplace add jake-w-liu/silence
claude plugin install silence@silence
```

## Use

In Codex, invoke it explicitly with the `$` prefix:

```text
$silence. Fix the failing test.
```

In Claude Code there is no `$` prefix — the skill activates automatically when you ask for the relevant task (its description matches), or you can ask for it by name:

```text
silence. Fix the failing test.
```

Codex or Claude Code can also select it when you ask for silence, quiet mode, no progress updates, final-only responses, or verified results only. While active, it suppresses optional interim messages for the whole task or goal by default.

## Contents

```text
.claude-plugin/
  plugin.json
  marketplace.json
skills/
  silence/
    SKILL.md
silence/
  SKILL.md
  agents/openai.yaml
```

The `skills/silence/SKILL.md` and `.claude-plugin/` files support Claude Code; the original `silence/SKILL.md` and `silence/agents/openai.yaml` are retained for the Codex installer.
