# Commit Message Generator

## Purpose

When asked to generate a commit message, always follow the project format below.

---

## Commit Message Format

```
[#<IssueID>] <type>(<scope>): <Task description>
```

### Examples

```
[#142] feat(auth): Add OAuth2 login with Google provider
[#98]  fix(cart): Resolve item quantity not updating on re-render
[#210] refactor(api): Extract user validation into separate service
[#--]  chore(deps): Upgrade React to v19 and update peer dependencies
```

> Use `[#--]` when the change is not tied to any specific issue.

---

## Valid Types

| Type       | When to use                                               |
|------------|-----------------------------------------------------------|
| `feat`     | Introduce a new feature                                   |
| `fix`      | Fix a bug                                                 |
| `refactor` | Code change that is neither a feat nor a fix              |
| `chore`    | Dependency updates, config, tooling — no logic impact     |
| `docs`     | Documentation or comment changes only                     |
| `test`     | Add or update tests                                       |

---

## How to Determine Each Field

### Issue ID

1. Check from the current branch name if available — e.g. `142-google-oauth` → `142`
2. If not found, use `--`

### `type`

Infer from the code change shown or described:

| Signal                                      | Type         |
|---------------------------------------------|--------------|
| New functionality added                     | `feat`       |
| Incorrect behavior corrected                | `fix`        |
| Restructured without behavior change        | `refactor`   |
| Only test files touched                     | `test`       |
| Only comments or `.md` files changed        | `docs`       |
| Lock file, `package.json`, CI config        | `chore`      |

### `scope`

Use the primary directory or module being changed:

| Changed area                          | Scope      |
|---------------------------------------|------------|
| `src/auth/`                           | `auth`     |
| `src/components/cart/`               | `cart`     |
| `src/api/` or `src/services/`        | `api`      |
| `src/store/`                          | `store`    |
| `tests/`                              | `test`     |
| `docs/`                               | `docs`     |
| Multiple unrelated modules            | omit scope |

### Task Description

- Start with an **imperative verb**: Add, Fix, Update, Remove, Refactor, Extract, Replace…
- No trailing period
- English only
- Max 72 characters
- Describe **what** changed, not **why**
---

## Breaking Changes

Append `!` after the type when the change breaks backward compatibility:

```
[#88] feat!(api): Replace REST endpoints with GraphQL — breaks v1 clients
```

---

## Constraints

- ❌ Never output without the `[#IssueID]` prefix
- ❌ Never invent an Issue ID — use `--` when not found
- ❌ Never write descriptions in a language other than English
- ❌ Never add emoji to the commit message
- ❌ Never use vague descriptions like `update code`, `fix bug`, `misc changes`
- ✅ Always output the message as a single-line string ready to paste into the terminal
---

## Usage in Copilot Chat

```
Generate a commit message for my staged changes
```

```
@workspace Generate a commit message for the changes in src/auth/
```
