# Go Style Guide

> https://google.github.io/styleguide/go/

## Overview

This documentation contains the complete Google Go Style Guide. It is intended for anyone who wants to write idiomatic, readable, and maintainable Go code.

## Documents

| Document | Description |
|----------|-------------|
| **[Style Guide](./guide.md)** | The foundation of Go Style - principles and core guidelines that all Go code should follow |
| **[Style Decisions](./decisions.md)** | Detailed style points with justifications and examples |
| **[Best Practices](./practices.md)** | Evolved patterns for solving common problems |

## Style Principles

The following are attributes of readable code, **in order of importance**:

1. **Clarity**: The code's purpose and rationale is clear to the reader
2. **Simplicity**: The code accomplishes its goal in the simplest way possible
3. **Concision**: The code has a high signal-to-noise ratio
4. **Maintainability**: The code is written such that it can be easily maintained
5. **Consistency**: The code is consistent with the broader codebase

## Key Definitions

- **Canonical**: Prescriptive and enduring rules, expected to remain stable
- **Normative**: Consistency standards for reviewers (may evolve over time)
- **Idiomatic**: Prevalent and recognizable Go patterns, preferred for familiarity

## Quick Reference

### Formatting

```bash
# All Go source files must conform to gofmt
gofmt -w .
```

### Naming

```go
// Use MixedCaps (no underscores)
func GetUserByID() {}  // Correct
func get_user_by_id() {} // Incorrect

// Package names: lowercase, no underscores
package httputil  // Correct
package http_util // Incorrect
```

### Error Handling

```go
// Always check errors
if err != nil {
    return fmt.Errorf("context: %w", err)
}

// Never ignore silently
_ = doSomething() // Avoid
```

## Resources

- [Effective Go](https://go.dev/doc/effective_go)
- [Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments)
- [Go FAQ](https://go.dev/doc/faq)
