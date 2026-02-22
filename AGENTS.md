# Repository Guidelines

## Project Structure & Module Organization
- `src/` contains application code (GJS + GTK4/Libadwaita).
- `src/components/` holds UI widgets and views.
- `src/state/` contains centralized reactive state (`ThemeState`).
- `src/services/` contains domain services (blueprints, wallhaven, thumbnails).
- `src/utils/` contains file, color, template, and integration helpers.
- `src/cli/` contains CLI entrypoints and commands.
- `templates/` stores theme templates rendered into generated configs.
- `docs/` contains user and developer-facing documentation.
- `examples/custom/` provides sample custom app template integrations.

## Build, Test, and Development Commands
- `./aether` - preferred local run path for development.
- `npm start` or `npm run dev` - launch app via `gjs -m src/main.js`.
- `npm run format` - format JavaScript files under `src/` with Prettier.
- `npm run format:check` - verify formatting without changing files.
- `aether --help` - list CLI options for generation/import/apply flows.

## Coding Style & Naming Conventions
- Language: ES modules (`"type": "module"`), GTK imports via `gi://...`.
- Indentation: 4 spaces; keep line length readable.
- Use `camelCase` for variables/functions and `PascalCase` for classes/components.
- Prefix private helpers/methods with `_` (for example `_applyCurrentTheme`).
- Add JSDoc for exported functions/classes.
- Run `npm run format` before opening a PR.

## Testing Guidelines
- There is no dedicated automated unit test suite in this repository yet.
- Validate changes with targeted manual checks:
  - Launch GUI (`./aether`) and verify affected flow end-to-end.
  - If CLI-related, run the specific command (for example `aether -l`).
  - Confirm output artifacts in `~/.config/aether/theme/` when relevant.
- For bug fixes, include clear reproduction and verification steps in the PR.

## Commit & Pull Request Guidelines
- Follow existing history style: short, imperative subject lines (for example `Fix GTK lifecycle errors`).
- Keep commits focused; avoid mixing refactors with behavior changes.
- PRs should include:
  - What changed and why
  - How it was tested (commands + outcomes)
  - Screenshots/GIFs for UI changes
  - Linked issue/PR number when applicable
