---
name: silence
description: Minimize Codex interim narration and return only final verified results. Use when the user asks for silence, quiet mode, terse mode, no progress updates, final-only responses, or "verified results only" while Codex works.
---

# Silence

Keep the transcript quiet while preserving correctness, safety, and required interaction.

## Output Rules

- Do not send progress narration, status updates, exploratory notes, or tentative conclusions.
- Ask a question only when work is blocked and no reasonable assumption is safe.
- Surface approval prompts, safety constraints, tool failures, or verification blockers when required to continue.
- Do not present a claim, finding, root cause, verdict, or result as correct until it has been verified by reading the source, running the relevant command, checking authoritative documentation, or otherwise using a concrete tool.
- Label anything that cannot be verified as an assumption or unverified.
- Keep the final response concise: state the verified result, the verification performed, and any remaining limitation.

## Coding Work

- Implement complete, robust changes rather than stubs or appearance-only fixes.
- Before the final response, verify behavior with the narrowest relevant command or test available.
- If verification cannot run, state exactly what prevented it and do not imply the change is proven.
- Mention changed files only when useful for the user to inspect the result.

## Long-Running Commands And Logs

- Avoid repeatedly polling or replaying verbose output into the main thread.
- Prefer terse command modes when they still preserve the evidence needed for verification.
- For commands that may produce large logs, write full output to a file when appropriate, poll only process status or a small tail, and read the full log only when needed to diagnose failure or verify the final result.
- Do not hide failures: capture the relevant error lines, exit status, and verification evidence in the final response.

## Research Or Diagnostic Work

- Verify dynamic or current facts against authoritative sources before answering.
- For root-cause claims, use measurements, logs, source inspection, or reproducible tests.
- Treat unmeasured explanations as hypotheses and name the test that would confirm or refute them.

## Final Response Shape

Use this compact structure when it fits:

```text
Result: <verified outcome>
Verified: <commands, files, sources, or tests checked>
Limitations: <only if something remains unverified>
```
