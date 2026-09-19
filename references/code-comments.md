# Code comments and docstrings

Comments are persistent repository content. Hold them to a higher bar than chat messages.

## When a comment earns its place

Add or keep a comment when it records information the code cannot express clearly, such as:

- a non-obvious reason or invariant;
- an external protocol, compatibility, or ordering constraint;
- a deliberate tradeoff;
- a surprising edge case;
- a temporary workaround with a removal condition;
- a public API contract, side effect, error, or ambiguous return value.

If clearer naming or structure can express the same fact, improve the code instead of adding commentary.

## Inline comments

Explain why the code takes this shape, not what each statement does.

Avoid:

```python
# Sort the queue by creation time.
queue.sort(key=lambda item: item.created_at)
```

Prefer:

```python
# Process older items first; newer items are more likely to change again.
queue.sort(key=lambda item: item.created_at)
```

Do not translate obvious control flow, variable names, or standard library calls into prose.

## Docstrings and public APIs

Document the contract rather than narrating the implementation. Include only relevant items:

- what callers can rely on;
- non-obvious input constraints;
- return semantics that types do not capture;
- externally visible side effects;
- important exceptions or failure behavior.

Simple private helpers and obvious accessors usually need no docstring.

## File headers and architectural notes

Add a file header only when the module's role or relationship to the system is not apparent from its name and public surface.

Use an architectural note when a future maintainer might reasonably "simplify" code and violate an important constraint. State the choice, reason, and tradeoff. Do not turn source files into design documents when a durable external document is the better home.

## Temporary notes

TODO, FIXME, and workaround comments should contain an actionable condition:

- what remains wrong or incomplete;
- what event allows removal;
- a durable issue or upstream reference when available.

An issue identifier is useful when it preserves traceability. Conversation history is not.

## Prohibited residue

Do not put assistant or session context into the repository, including:

- "based on your request";
- "as discussed earlier";
- "the improved approach" without naming the actual constraint;
- rejected approaches that have no lasting architectural relevance;
- investigation logs, tool traces, or claims about how much work was done.

Do not add promotional judgments such as "clean", "elegant", "robust", or "production-ready" unless the repository defines a concrete standard and the comment must record it.

## Review existing comments

When changing nearby behavior, update or remove comments that no longer match it. A stale comment is worse than no comment.
