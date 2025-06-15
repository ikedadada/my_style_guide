# TypeScript Style Guide

## 🎯 Purpose

This guide defines shared TypeScript coding conventions to ensure AI agents can generate code that reflects my personal coding style, regardless of frontend, backend, or CLI context.

---

## 📁 Project Structure

- Code is organized by **functionality**, not by type (e.g., no flat `utils/`, but meaningful folders like `file`, `excel`, `auth`).
- Use `src/` for application source and `test/` for unit/integration tests.
- Projects are separated cleanly into frontend/backend if applicable.
- Configuration files (`tsconfig.json`, `.eslintrc`, `.env`, etc.) live at the root level.
- Avoid unnecessary nesting; prefer a flat, discoverable structure.

---

## 🧠 Naming Conventions

- **camelCase** for variables, functions, and file names.
- **PascalCase** for classes, types, interfaces, and React components.
- **UPPER_SNAKE_CASE** for constants (when semantically justified).
- File names match the main export (e.g., `excelUtils.ts`).
- No Hungarian notation, underscores, or abbreviations unless widely accepted (`id`, `url`, etc.).
- Acronyms are consistently capitalized (`HTTP`, `ID`, etc.).

---

## 🧾 Typing & Language Features

- **Strict typing is always enabled**; avoid `any` unless absolutely necessary.
- Use `interface` for object shapes, `type` for unions and mapped types.
- Prefer explicit return types on exported functions.
- Use `unknown` over `any` for unknown values.
- Use TypeScript utility types (`Partial`, `Pick`, `Record`) to avoid verbose definitions.
- Prefer function components and arrow functions where applicable.

---

## 🔧 Implementation Style

- Write **small, composable functions** with minimal side effects.
- Use **early returns** to simplify control flow.
- Avoid deeply nested logic or large inline callbacks.
- Group related utility functions into dedicated modules (`xxxUtils.ts`).
- Separate I/O (e.g., file, API) from pure logic.
- Extract config, constants, and default values into their own modules.

---

## 🔥 Error Handling

- Use `try/catch` around I/O, async, or external code.
- Return informative, user-facing error messages where applicable.
- Avoid silent failure: log, throw, or return structured errors as needed.
- Use custom error types when handling multiple failure cases.
- Never use `throw` for normal control flow.

---

## 🧪 Testing

- Test files use `.test.ts` or `.spec.ts` extensions.
- Use **table-driven tests** where possible for clarity.
- Avoid external assertion libraries unless necessary; prefer native `expect` or test-runner assertions.
- Use `beforeEach/afterEach` or setup helpers to keep tests DRY.
- Structure tests by feature, not by layer (e.g., `auth/login.test.ts` instead of `unit/`, `integration/`).

---

## 🧰 Tooling & Automation

- Use `tsconfig.json` with `strict: true` and appropriate `baseUrl`/`paths` when aliases are needed.
- Lint with ESLint or Biome; format automatically via Prettier, Biome, or ESLint `--fix`.
- Keep `package.json` scripts minimal and relevant (`dev`, `build`, `test`, `lint`).
- Prefer `.env` or config files over hardcoded values for environment-dependent settings.
- Use Docker and `.dockerignore` if containerization is expected; otherwise keep tooling lightweight.

---

## 📦 Module Imports

- Use **ES Modules** (`import/export`) exclusively.
- Avoid wildcard imports (`import * as X`); prefer named imports.
- Order imports: Node > third-party > internal.
- Use relative paths only within the same module scope; otherwise define clean path aliases.
- Never use dynamic `require()` unless absolutely necessary.

---

## 💬 Comments & Documentation

- Favor **clear naming** over excessive comments.
- Use **JSDoc-style comments** on exported functions, complex utilities, and public APIs.
- Avoid stating the obvious (`// increment i`); explain why, not what.
- Maintain `README.md` per project with purpose, setup, usage, and scripts.
- Keep comments in English, even in non-public codebases.

---

## 🧭 Summary

This guide provides the foundation for AI-assisted TypeScript development that mirrors my coding standards:
**modular, type-safe, explicit, and clean.**

Language-specific quirks and framework preferences should be layered on top of this core foundation as needed.
