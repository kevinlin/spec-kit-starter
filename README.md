# Spec-Kit Starter

Welcome to your Spec-Kit project! This template provides a spec-driven development workflow powered by AI agents.

## Setup (Manual Install)

If your environment doesn't support `uv` or the Specify CLI (e.g., restricted Windows laptops), you can set up Spec-Kit manually:

1. **Copy folders** — Copy `.github/` and `.specify/` from this repo into your target project's root directory.
2. **Apply VS Code settings** — Merge the contents of `.vscode/settings.json` into your target project's `.vscode/settings.json`:
   ```jsonc
   {
     "chat.promptFilesRecommendations": {
       "speckit.constitution": true,
       "speckit.specify": true,
       "speckit.plan": true,
       "speckit.tasks": true,
       "speckit.implement": true
     },
     "chat.tools.terminal.autoApprove": {
       ".specify/scripts/bash/": true,
       ".specify/scripts/powershell/": true
     }
   }
   ```

## Agent Folder Security

> Some agents may store credentials, auth tokens, or other identifying and private artifacts in the agent folder within your project.
> Consider adding `.github/` (or parts of it) to `.gitignore` to prevent accidental credential leakage.

## Next Steps

You're already in the project directory! Start using slash commands with your AI agent:

| Step | Command | Description |
|------|---------|-------------|
| 1 | `/speckit.constitution` | Establish project principles |
| 2 | `/speckit.specify` | Create baseline specification |
| 3 | `/speckit.plan` | Create implementation plan |
| 4 | `/speckit.tasks` | Generate actionable tasks |
| 5 | `/speckit.implement` | Execute implementation |

## Enhancement Commands

Optional commands to improve spec quality and confidence:

| Command | When to Use | Description |
|---------|-------------|-------------|
| `/speckit.clarify` | Before `/speckit.plan` | Ask structured questions to de-risk ambiguous areas |
| `/speckit.analyze` | After `/speckit.tasks`, before `/speckit.implement` | Cross-artifact consistency and alignment report |
| `/speckit.checklist` | After `/speckit.plan` | Generate quality checklists to validate requirements completeness, clarity, and consistency |

## Project Structure

```
.github/
  agents/          # Agent definitions for each workflow step
  prompts/         # Prompt files for each slash command
.specify/
  memory/          # Persistent context (e.g., constitution)
  scripts/         # Automation scripts
  templates/       # Templates for specs, plans, tasks, etc.
```
