---
description: 'TypeScript documentation, commenting, and formatting standards'
applyTo: '**/*.ts'
---

# TypeScript Instructions

## Comments and API Documentation

- Comment on intent and non-obvious decisions: explain why code exists or why an approach was chosen, not what the next line already says.
- Prefer clear names and small functions over comments that narrate routine mechanics.
- Keep comments accurate when changing related code; update them or remove them when their explanation is no longer true.
- Add a TSDoc comment to every exported function in `db/` and `src/lib/`. State its purpose and document every parameter and the return value with `@param` and `@returns` tags. Describe injectable `db` parameters so callers know they allow the helper to use either the application database or a test database.
- Document exported types and values when their purpose or constraints are not self-evident.

```ts
/**
 * Return game ids in title order for deterministic static routes.
 * @param db Database instance; inject an in-memory database in tests.
 * @returns Game ids ordered by title.
 */
export async function getAllGameIds(db: Database): Promise<number[]> {
  // ...
}
```

## Formatting

- Use two spaces for indentation, single quotes for strings, and terminate statements with semicolons.
- Include trailing commas in multiline arrays, objects, and parameter lists.
- Remove trailing whitespace and end files with a newline.
- Follow the ESLint rules in `eslint.config.js`; do not disable a formatting rule to avoid correcting code.
- Use explicit parameter and return types, especially for exported functions in `db/` and `src/lib/`.
