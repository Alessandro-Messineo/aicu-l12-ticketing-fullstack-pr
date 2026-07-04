# Repository Instructions

This is the student-facing L12 starter for a small full-stack ticketing lab.

## Goal

Implement:

```txt
priority + sourceChannel -> urgencyLabel
```

`urgencyLabel` must be calculated on the server, persisted, returned by the API, and displayed by the UI.

## Product rule

Valid `sourceChannel` values:

```txt
email
telefono
chat
```

Invalid case to preserve:

```txt
whatsapp -> 400 fieldErrors.sourceChannel
```

Expected mapping:

| priority | sourceChannel | urgencyLabel |
| --- | --- | --- |
| alta | telefono | intervento rapido |
| alta | chat | prioritario |
| alta | email | prioritario |
| normale | telefono | da gestire |
| normale | chat | da gestire |
| normale | email | standard |
| bassa | telefono | monitorare |
| bassa | chat | monitorare |
| bassa | email | monitorare |

## Boundaries

- Do not calculate `urgencyLabel` in `src/main.js`.
- Do not implement `responseDueAt`.
- Do not add auth, assignments, notifications, duplicate ticket detection, analytics, advanced filters, or a full test suite.
- Keep the UI close to the existing dark dashboard style.
- Keep copy in Italian.

## Workflow

- Use `pnpm` only.
- Run `pnpm dev` to start the app.
- Run `pnpm check` after editing JavaScript.
- Prefer small, file-by-file patches.
- Verify each step with visible evidence: payload, API response, error response, or UI output.

## Safety

Never read, create, paste, or commit credentials, tokens, `.env` files, personal data, or private screenshots.
