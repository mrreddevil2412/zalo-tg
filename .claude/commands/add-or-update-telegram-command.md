---
name: add-or-update-telegram-command
description: Workflow command scaffold for add-or-update-telegram-command in zalo-tg.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-telegram-command

Use this workflow when working on **add-or-update-telegram-command** in `zalo-tg`.

## Goal

Adds a new Telegram bot command or updates the command menu, often including handler logic and registration.

## Common Files

- `src/telegram/handler.ts`
- `src/index.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or add logic in src/telegram/handler.ts to implement the command.
- Update src/index.ts to register the command with setMyCommands.
- Optionally update src/zalo/handler.ts or src/zalo/client.ts if Zalo integration is needed.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.