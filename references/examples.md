# Before and after examples

Use these examples to recognize information problems, not as fixed wording templates.

## Completion summary

Before:

```text
I have successfully implemented a comprehensive and robust validation mechanism that significantly improves reliability across complex edge cases.
```

After:

```text
`parse_target()` now rejects an empty `repo_id`. Three regression tests pass in `tests/test_target.py`.
```

The revision names the symbol, changed behavior, and verification. It does not merely shorten the original.

## Honest uncertainty

Before:

```text
The issue appears to be related to several potentially complex networking factors.
```

After:

```text
Requests time out after the gateway, but current logs do not show whether the wait is in PostgreSQL or the downstream billing API.
```

The revision keeps uncertainty while identifying the known boundary and missing evidence.

## Progress update

Before:

```text
I have completed an initial review and will now continue with a deeper investigation of the relevant implementation details.
```

After:

```text
The parser accepts the invalid input before schema validation. I am tracing why this endpoint bypasses `TargetSchema`.
```

## Review finding

Before:

```text
Overall, this is a solid implementation. One area that may benefit from additional consideration is the cache-key construction, which could potentially create issues in some multi-tenant scenarios.
```

After:

```text
[P1] `auth/cache.py:84` — The cache key omits tenant ID, so tenants sharing a user ID can receive the same cached permissions.
```

## No review findings

Before:

```text
The implementation demonstrates good adherence to best practices and no major issues were identified. As always, additional testing could further improve confidence.
```

After:

```text
No actionable defects found. I did not run the Windows-specific tests.
```

Only mention a validation gap that actually exists and affects confidence.

## Code comment

Before:

```python
# Iterate over each user and process the user.
for user in users:
    process(user)
```

After:

```python
for user in users:
    process(user)
```

No comment is better when the code already says everything.

## Abstract benefit

Before:

```text
This refactor improves maintainability and creates a more scalable architecture.
```

After:

```text
Token refresh now lives in `TokenRefresher` instead of three request handlers, removing 74 lines of duplicated retry logic.
```

Use the concrete mechanism. Let the reader decide how much it improves maintainability.

## Requested teaching depth

Conciseness must not override the user's request. If the user asks for a detailed explanation of a lock-free queue, explain the algorithm, memory ordering, invariants, and failure modes. Lead with the direct answer, but do not compress away the material they asked to learn.

## Complex code explanation

Before:

```text
The CLI uses a robust multi-layer configuration architecture:

1. The argument layer reads command-line flags.
2. The repository layer reads project configuration.
3. The user layer reads global configuration.
4. The resolution layer combines the values.
5. The validation layer checks the result.

This layered approach provides flexible and reliable configuration management.
```

After:

```text
The CLI resolves configuration in this order: command-line flags override repository settings, which override user settings. `resolve_config()` performs that merge and validates the winning values once, so `--timeout 0` fails even when the config file contains a valid timeout.
```

The revision does more than remove headings. It states the precedence rule and shows one consequence. Add variants only when they change that rule.

## Evidence without a source dump

Before:

```text
Arguments are parsed in `cli/args.py:42`.
Repository settings are loaded in `config/repo.py:31`.
User settings are loaded in `config/user.py:27`.
Precedence is implemented in `config/resolve.py:88`.
Validation is implemented in `config/schema.py:14`.
```

After:

```text
`resolve_config()` applies flag, repository, and user settings in precedence order (`config/resolve.py:88`), then validates the merged result with `ConfigSchema` (`config/schema.py:14`).
```

Keep enough anchors to verify the mechanism. A path-by-path tour makes the reader reconstruct the explanation from the repository layout.
