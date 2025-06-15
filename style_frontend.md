# Frontend Style Guide

## 🎯 Purpose

This guide defines a set of frontend development principles derived from my actual coding style.
Its goal is to ensure that AI agents can generate frontend code that is structurally and stylistically consistent with my own.

---

## 📁 Project Structure

- Organize code primarily by **type**, using top-level directories such as:

  - `components/` for reusable UI parts
  - `pages/` or `app/` for route-based views
  - `utils/` or `lib/` for logic utilities
  - `public/` for static assets

- Feature-specific logic may be grouped under `module/` or equivalent if needed.

- **Separate backend and frontend clearly** in larger systems (e.g., `frontend/`, `backend/`).

- Place configuration files (`tsconfig.json`, `eslint.config.mjs`, `biome.json` etc.) at the root level.

---

## 🧠 Naming Conventions

- **Directories**: lowercase and plural (e.g., `components`, `pages`, `utils`)
- **Component Directories**: Use the same name and case as the component (PascalCase).
  - Example: `UserCard/UserCard.tsx`,`UserCard/index.tsx`
- **Component files**: `PascalCase` (e.g., `UserCard.tsx`)
- **Utility and config files**: `camelCase` or lowercase (e.g., `excelUtils.ts`, `vite.config.ts`)
- **Constants**: `SCREAMING_SNAKE_CASE`
- **Variables and functions**: `camelCase`

- **All names must be descriptive and avoid ambiguity.**

---

## 🧩 Component Design

- **Use function components exclusively.**
- **Compose UI from small, focused components.**
- **Extract business logic into custom hooks to improve testability and separation of concerns.**
- Avoid embedding complex logic directly in components.
- Co-locate related files (e.g., stories or styles) where it improves maintainability.
- Prefer **controlled components** for form and input elements.

---

### 🔖 Component Directory Structure

Each component should reside in its own directory with the following structure:

```
[ComponentName]/
├── index.ts                  # Barrel export for the component
├── [ComponentName].tsx       # Main React component
├── [hooks].ts                # Custom hooks specific to the component
├── [ComponentName].stories.ts # Storybook configuration
├── [ComponentName].test.ts   # Component test
└── [hooks].test.ts           # Hook test
```

- Keep hooks and their tests inside the component folder when they are tightly coupled.
- Use this pattern consistently across all feature-level and shared components.

## 🎨 Styling

- **Use utility-first CSS (e.g., Tailwind CSS)** as the main styling approach.
- Minimize custom CSS; keep it simple and scoped.
- Apply **mobile-first responsive design** via utility class prefixes.
- Use accessible UI libraries when appropriate (e.g., shadcn/ui).

---

## ⚛️ State Management

- **Use React local state (`useState`, `useReducer`) for isolated concerns.**
- Use Context API only for global/shared concerns.
- **Minimize external state libraries** unless necessary.
- Memoize hooks/selectors when performance is critical.

---

## 🧪 Testing

- **Test logic extracted into hooks and utilities.**
- Use tools like **Jest** or **Vitest**, depending on the stack.
- Organize tests either in a `test/` folder or alongside source files.
- Write clear and descriptive `describe` / `it` blocks.
- Use **Storybook** to document and verify component behavior visually.

---

## ♿ Accessibility

- **Write semantic HTML and support keyboard navigation.**
- Provide useful `aria` attributes.
- Avoid inaccessible visual-only cues.

---

## ⚙️ Tooling

- **Use TypeScript throughout for type safety.**
- Enforce consistent style with **ESLint** and **Prettier/Biome**.
- Use modern build systems (e.g., Vite, Next.js) and adopt sensible defaults.
- Configure path aliases for clean import resolution.

---

## ⛳ Summary

This guide reflects how I structure and write frontend code:

- **Consistent structure based on type**
- **Function-based, composable components**
- **Logic extracted into testable custom hooks**
- **Tailwind-first styling**
- **Minimal, local-first state management**
- **Readable, testable, and accessible design**

AI agents should follow this guide to ensure their output aligns with my frontend development style.
