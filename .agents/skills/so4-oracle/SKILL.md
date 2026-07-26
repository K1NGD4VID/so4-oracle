```markdown
# so4-oracle Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the `so4-oracle` Rust codebase. You'll learn about file naming, import/export styles, commit message conventions, and how to write and organize tests. This guide also provides step-by-step workflows and suggested commands for common development tasks.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `oracleClient.rs`, `priceFetcher.rs`

### Import Style
- Use **relative imports** for referencing modules within the project.
  - Example:
    ```rust
    use crate::utils::math;
    use super::oracleClient;
    ```

### Export Style
- Use **named exports** to expose specific items from modules.
  - Example:
    ```rust
    pub struct OracleClient { /* ... */ }
    pub fn fetch_price() { /* ... */ }
    ```

### Commit Messages
- Follow the **Conventional Commits** format.
- Use the `fix` prefix for bug fixes.
  - Example:
    ```
    fix: correct price calculation for edge cases
    ```

## Workflows

### Code Commit Workflow
**Trigger:** When making code changes that need to be committed.
**Command:** `/commit`

1. Make your code changes following the coding conventions.
2. Write a commit message using the conventional format (e.g., `fix: ...`).
3. Commit your changes.
   ```sh
   git add .
   git commit -m "fix: update oracle response parsing"
   ```

### Testing Workflow
**Trigger:** When you want to run or write tests.
**Command:** `/test`

1. Write test files using the `*.test.*` naming pattern.
   - Example: `oracleClient.test.rs`
2. Use Rust's built-in test framework (e.g., `#[test]`).
   - Example:
     ```rust
     #[cfg(test)]
     mod tests {
         #[test]
         fn test_fetch_price() {
             // test logic here
         }
     }
     ```
3. Run tests with:
   ```sh
   cargo test
   ```

## Testing Patterns

- Test files are named with the `*.test.*` pattern (e.g., `module.test.rs`).
- Tests use Rust's built-in test framework.
- Place tests in the same file as the module or in separate test files.
- Example test:
  ```rust
  #[cfg(test)]
  mod tests {
      #[test]
      fn test_oracle_response() {
          assert_eq!(2 + 2, 4);
      }
  }
  ```

## Commands
| Command   | Purpose                                 |
|-----------|-----------------------------------------|
| /commit   | Commit code changes using conventions   |
| /test     | Run or write tests                      |
```
