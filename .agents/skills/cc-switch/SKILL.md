```markdown
# cc-switch Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `cc-switch` repository, a Rust codebase with a focus on clear structure and maintainable code. You'll learn about file naming, import/export styles, commit message conventions, and how to write and run tests in this project.

## Coding Conventions

### File Naming
- Use **PascalCase** for file and module names.
  - **Example:**  
    `SwitchHandler.rs`  
    `NetworkManager.rs`

### Import Style
- Use **aliasing** when importing modules or crates.
  - **Example:**
    ```rust
    use std::collections::HashMap as Map;
    use crate::SwitchHandler as Handler;
    ```

### Export Style
- Use **named exports** for public items.
  - **Example:**
    ```rust
    pub struct SwitchConfig { /* ... */ }
    pub fn initialize_switch() { /* ... */ }
    ```

### Commit Messages
- Follow the **Conventional Commits** specification.
  - Prefixes: `feat`, `fix`
  - Example:
    ```
    feat: add support for dynamic port switching
    fix: resolve panic on empty config
    ```

## Workflows

### Feature Development
**Trigger:** When adding a new feature  
**Command:** `/feature`

1. Create a new branch for your feature.
2. Use PascalCase for new files/modules.
3. Use aliasing for imports as needed.
4. Export new structs/functions with `pub`.
5. Commit changes with a `feat:` prefix and a concise description.
6. Open a pull request.

### Bug Fixing
**Trigger:** When fixing a bug  
**Command:** `/fix`

1. Create a new branch for your bugfix.
2. Make necessary code changes.
3. Use aliasing for imports as needed.
4. Commit changes with a `fix:` prefix and a concise description.
5. Open a pull request.

## Testing Patterns

- Test files follow the `*.test.*` naming pattern.
  - **Example:** `SwitchHandler.test.rs`
- Testing framework is not explicitly specified; use Rust's built-in test framework unless otherwise noted.
- Example test:
  ```rust
  #[cfg(test)]
  mod tests {
      use super::*;

      #[test]
      fn test_switch_initialization() {
          let config = SwitchConfig::default();
          assert!(initialize_switch(config).is_ok());
      }
  }
  ```

## Commands
| Command   | Purpose                                 |
|-----------|-----------------------------------------|
| /feature  | Start a new feature development workflow|
| /fix      | Start a new bug fixing workflow         |
```
