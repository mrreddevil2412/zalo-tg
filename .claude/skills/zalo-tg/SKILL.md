```markdown
# zalo-tg Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill covers the development patterns and workflows for the `zalo-tg` TypeScript codebase, which bridges Zalo and Telegram messaging platforms. It outlines coding conventions, common workflows (such as adding new commands, updating integrations, and fixing bugs), and provides guidance on testing and command usage. Whether you're contributing new features or maintaining the project, this guide will help you follow established practices.

## Coding Conventions

- **File Naming:**  
  Use camelCase for file names.  
  _Example:_  
  ```
  zaloClient.ts
  messageForwarder.ts
  ```

- **Import Style:**  
  Use relative imports for modules within the project.  
  _Example:_  
  ```typescript
  import { sendMessage } from './zaloClient';
  ```

- **Export Style:**  
  Prefer named exports.  
  _Example:_  
  ```typescript
  // In zaloClient.ts
  export function sendMessage() { ... }
  ```

- **Commit Messages:**  
  Follow [Conventional Commits](https://www.conventionalcommits.org/) with prefixes like `fix`, `feat`, `chore`, `docs`, `perf`.  
  _Example:_  
  ```
  feat: add support for group message forwarding
  fix: prevent duplicate reaction forwarding
  ```

## Workflows

### Add or Update Telegram Command
**Trigger:** When you want to add a new Telegram bot command or update the command menu.  
**Command:** `/add-telegram-command`

1. Edit or add logic in `src/telegram/handler.ts` to implement the command.
   ```typescript
   // src/telegram/handler.ts
   export function handleNewCommand(ctx) {
     // Command logic here
   }
   ```
2. Update `src/index.ts` to register the command with `setMyCommands`.
   ```typescript
   // src/index.ts
   bot.setMyCommands([
     { command: 'newcommand', description: 'Description' },
     // ...other commands
   ]);
   ```
3. Optionally update `src/zalo/handler.ts` or `src/zalo/client.ts` if Zalo integration is needed.

---

### Add or Update Zalo Integration Feature
**Trigger:** When you want to add or fix Zalo-related features (e.g., message forwarding, reactions, group support).  
**Command:** `/update-zalo-feature`

1. Edit `src/zalo/handler.ts` to implement or fix the feature.
   ```typescript
   // src/zalo/handler.ts
   export function handleZaloMessage(msg) {
     // Feature logic here
   }
   ```
2. Optionally update `src/store.ts` for caching or state management.
   ```typescript
   // src/store.ts
   export function cacheMessage(id, data) { ... }
   ```
3. Optionally update `src/telegram/handler.ts` if Telegram-side logic is affected.

---

### Add or Update README or Documentation
**Trigger:** When you want to update the documentation or README.  
**Command:** `/update-docs`

1. Edit `README.md` and/or `README.vi.md`.
2. Optionally add or remove media files (e.g., setup videos).

---

### Fix Bug in Message or Reaction Forwarding
**Trigger:** When you notice bugs in message/reaction forwarding or echo behavior.  
**Command:** `/fix-forwarding-bug`

1. Edit `src/zalo/handler.ts` to fix forwarding logic.
   ```typescript
   // src/zalo/handler.ts
   export function forwardMessage(msg) {
     if (!isDuplicate(msg)) {
       // Forwarding logic
     }
   }
   ```
2. Optionally update `src/store.ts` for deduplication or state tracking.
   ```typescript
   // src/store.ts
   export function isDuplicate(msg) { ... }
   ```
3. Optionally update `src/telegram/handler.ts` if Telegram-side logic is involved.

---

### Add or Update Updater Feature
**Trigger:** When you want to add or improve update checking or update-related commands.  
**Command:** `/add-updater-feature`

1. Edit `src/updater.ts` to implement update logic.
   ```typescript
   // src/updater.ts
   export function checkForUpdates() { ... }
   ```
2. Update `src/index.ts` and `src/telegram/handler.ts` to add commands or notifications.
   ```typescript
   // src/telegram/handler.ts
   export function handleUpdateCommand(ctx) {
     // Notify user about updates
   }
   ```

## Testing Patterns

- **Test File Naming:**  
  Test files follow the pattern `*.test.*` (e.g., `handler.test.ts`).

- **Framework:**  
  No specific testing framework detected.  
  _Tip:_ Use your preferred TypeScript-compatible test runner (like Jest or Mocha).

- **Example Test File:**  
  ```typescript
  // handler.test.ts
  import { handleZaloMessage } from './handler';

  test('should process message correctly', () => {
    // Test logic here
  });
  ```

## Commands

| Command                | Purpose                                                        |
|------------------------|----------------------------------------------------------------|
| /add-telegram-command  | Add or update a Telegram bot command and its registration      |
| /update-zalo-feature   | Implement or fix a Zalo integration feature                   |
| /update-docs           | Update README or documentation files                          |
| /fix-forwarding-bug    | Fix bugs in message or reaction forwarding                    |
| /add-updater-feature   | Add or update the auto-update checker or related commands     |
```
