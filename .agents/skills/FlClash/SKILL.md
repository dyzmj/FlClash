```markdown
# FlClash Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill covers the development patterns and conventions used in the FlClash repository, a Go codebase with no detected framework. You'll learn about file organization, import/export styles, commit message habits, and how to write and run tests. This guide is ideal for developers contributing to FlClash or projects with similar patterns.

## Coding Conventions

### File Naming
- **Convention:** Use `snake_case` for all file names.
- **Example:**  
  ```plaintext
  player_manager.go
  game_logic.go
  ```

### Import Style
- **Convention:** Use **relative imports** within the project.
- **Example:**
  ```go
  import (
      "fmt"
      "../utils"
  )
  ```

### Export Style
- **Convention:** Use **named exports** (capitalize exported functions/types).
- **Example:**
  ```go
  // Exported function
  func StartGame() {}

  // Unexported function
  func calculateScore() {}
  ```

### Commit Messages
- **Style:** Freeform, no strict prefixes.
- **Average Length:** ~20 characters.
- **Example:**
  ```
  fix bug in player join
  add new battle mode
  ```

## Workflows

### Adding a New Feature
**Trigger:** When implementing new functionality.
**Command:** `/add-feature`

1. Create a new `.go` file using `snake_case` for the filename.
2. Write your code, using relative imports for internal packages.
3. Export any functions/types that need to be accessed outside the package by capitalizing their names.
4. Write corresponding test files named `*_test.go`.
5. Commit changes with a concise, descriptive message.

### Fixing a Bug
**Trigger:** When resolving a reported or discovered issue.
**Command:** `/fix-bug`

1. Locate the relevant code section.
2. Apply the fix, following code style conventions.
3. Update or add tests in the corresponding `*_test.go` file.
4. Commit the fix with a brief, descriptive message.

### Writing and Running Tests
**Trigger:** When verifying code correctness.
**Command:** `/run-tests`

1. Write test cases in files matching the pattern `*_test.go`.
2. Use Go's built-in testing package.
3. Run tests using the Go toolchain:
   ```sh
   go test ./...
   ```
4. Review and address any failing tests.

## Testing Patterns

- **Framework:** No specific framework detected; uses Go's standard `testing` package.
- **File Pattern:** Test files are named with the pattern `*_test.go`.
- **Example:**
  ```go
  // player_manager_test.go
  package main

  import "testing"

  func TestStartGame(t *testing.T) {
      // test logic here
  }
  ```

## Commands
| Command      | Purpose                                 |
|--------------|-----------------------------------------|
| /add-feature | Start the process to add a new feature  |
| /fix-bug     | Begin workflow to fix a bug             |
| /run-tests   | Run all tests in the codebase           |
```
