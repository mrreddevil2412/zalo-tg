---
name: add-or-update-zalo-integration-feature
description: Workflow command scaffold for add-or-update-zalo-integration-feature in zalo-tg.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-zalo-integration-feature

Use this workflow when working on **add-or-update-zalo-integration-feature** in `zalo-tg`.

## Goal

Implements or fixes a Zalo integration feature, often involving message handling, reactions, or group logic.

## Common Files

- `src/zalo/handler.ts`
- `src/store.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit src/zalo/handler.ts to implement or fix the feature.
- Optionally update src/store.ts for caching or state management.
- Optionally update src/telegram/handler.ts if Telegram-side logic is affected.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.