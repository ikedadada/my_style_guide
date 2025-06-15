# Python Style Guide

## 🎯 Purpose

This guide defines the core Python coding principles I follow, abstracted across domains.  
It exists to enable AI agents to write Python code that is stylistically and structurally consistent with my personal preferences.

---

## 📁 Project Structure

- Organize code by **domain responsibility**, not by type (e.g., `optimizer/`, `io/`, `cli/`).
- Use a `main.py` or `app.py` as the clear entry point.
- Define reusable logic in importable modules or packages.
- Use `__main__` guard for scripts:

  ```python
  if __name__ == "__main__":
      main()
  ```

- Keep external configuration minimal; prefer self-contained modules.

---

## 🧠 Naming Conventions

- Use `snake_case` for variables, functions, files, and module names.
- Use `PascalCase` for class names.
- Use `ALL_CAPS` for constants when appropriate.
- Prefer descriptive, meaningful names; avoid unnecessary abbreviations.
- Preserve consistency for acronyms (e.g., `user_id`, `parse_url`, `APIClient`).

---

## 🔧 Implementation Style

- Prioritize **clarity over cleverness**.
- Keep functions small and **single-purpose**.
- Prefer **explicit code paths** and **early returns** over nested logic.
- Use **pure functions** when possible; isolate side effects.
- Use `assert` or conditional guards to enforce invariants.

---

## 🛠️ Typing & Parameters

- Prefer dynamic typing with clear naming and usage.
- Use type hints when complexity increases or public API is exposed.
- Avoid `any`-style flexibility unless justified; be deliberate about accepted input.
- Pass configurations explicitly as function parameters; avoid hidden state.
- Use default parameter values thoughtfully to reduce required setup.

---

## 🚫 Error Handling

- Fail early on invalid input with `raise ValueError(...)` or `assert`.
- Avoid catching broad exceptions; catch what is necessary and re-raise otherwise.
- Never silence errors; log or explain when suppressing is justified.
- Design code to surface problems clearly, not to obscure them.

---

## 💬 Comments & Documentation

- Use comments to explain **intent**, not obvious code.
- Write docstrings for all public classes and functions.
- Structure documentation as:

  ```python
  def do_something(x):
      """Does something important.

      Args:
          x (int): Description of x.

      Returns:
          int: Description of return value.
      """
  ```

- Keep README and example usage files concise and accurate.

---

## 🧪 Testing Approach

- **Automate tests whenever feasible**, following the common guideline of "Automate Everything Repeatable".
- Use `pytest` or similar frameworks for **unit tests** and **integration tests**.
- Small scripts may include example-based verification, but this should **supplement**, not replace, automated tests.
- Keep test setup lightweight and reproducible.

---

## 🧰 Tooling & Dependencies

- Use standard libraries where possible.
- Keep dependencies minimal and well-scoped.
- Prefer explicit requirements (`requirements.txt`) when needed.
- Avoid complex environments or dependency managers unless justified.

---

## ⛳ Summary

This guide defines my Python coding philosophy: clear, modular, minimal, and explicit.  
AI agents should follow this structure to ensure their output aligns naturally with code I would write.
