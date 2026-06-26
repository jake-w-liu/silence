# Silence

Silence is a Codex skill for quiet, final-only work. It tells Codex to avoid interim narration and return only verified final results, while still allowing required approval prompts, blocker questions, tool failures, and safety constraints.

## Install

In Codex, run:

```text
$skill-installer https://github.com/jake-w-liu/silence/tree/main/silence
```

Restart Codex after installation so the new skill is discovered.

## Use

Invoke it explicitly:

```text
$silence. Fix the failing test.
```

Codex can also select it when you ask for silence, quiet mode, no progress updates, final-only responses, or verified results only.

## Contents

```text
silence/
  SKILL.md
  agents/openai.yaml
```
