# Vibe check

## Trigger

The user runs `/vibe-check` or asks for a "vibe check" or "what would you clean" without applying changes.

## Principle

Same **analyze-first, stack-agnostic** approach as vibe-clean, but **no edits** — only report what would be done.

## Workflow

1. **Analyze first:** Detect language, file type, and project conventions from the file/repo (same as vibe-clean).
2. **Scope:** Current file, selection, or user-specified scope.
3. **Run the same checks** as vibe-clean: format, noise, dead code, naming, structure. For each finding: **location** (file, line/region), **issue**, and **suggested change**.
4. **Output:** A **vibe report** listing all findings by category (Format, Noise, Dead code, Naming, Structure) with file/line and suggestion. End with a one-line summary (e.g. "Would clean 8 items: 3 format, 2 noise, 2 dead code, 1 naming."). Do **not** apply any edits.
5. **Tone:** Friendly and concise. Optionally add "Run `/vibe-clean` to apply these changes."

## Guardrails

- Do not modify any files. Report only.
- Infer stack and conventions from the code; do not assume a tech stack.
