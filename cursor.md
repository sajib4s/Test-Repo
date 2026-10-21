# TestProject Guidelines

Follow these rules when working in this Node.js, TypeScript, and Next.js project. Read this file before writing code.

## Goals

- Write small, clear, maintainable solutions.
- Do only what was asked. Do not add extra files or refactors.
- Treat TypeScript types as the source of truth. Avoid `any`.

## Node.js

- Use ESM (`import` / `export`) when the project already uses ESM.
- Keep side effects inside functions, not at module startup.
- Isolate filesystem, network, and process env access in their own layer.
- Read secrets from `process.env` only. Never hardcode them.
- Use `async` / `await`. Do not leave unhandled promises.
- Do not swallow errors. Forward them with a status code and message.
- Do not commit `node_modules` or build output.

## TypeScript

- Assume `strict` mode. Do not bypass types with `as any` or `@ts-ignore`.
- Type public APIs, props, and function parameters explicitly.
- Keep shared types in `types/` or next to the module. Do not duplicate interfaces.
- Prefer unions and discriminated unions when states differ.
- Prefer `as const` objects or string unions over `enum`.
- Validate at runtime with a schema (for example Zod), not type casts alone.

## Next.js

- Assume the App Router: put routes, layouts, and pages in `app/`.
- Server Components are the default. Add `"use client"` only for client state, events, or browser APIs.
- Fetch data on the server when possible. Keep client data limited to interactive UI.
- Put APIs and mutations in `app/api` route handlers or server actions.
- Never expose secrets in the client bundle. Use `NEXT_PUBLIC_` only for public values.
- Use `next/image` for images and `next/link` for links.
- After UI changes, verify the affected routes in the browser.

## Files and structure

```
app/           routes, layouts, pages, API
components/    UI components
lib/           utilities, server helpers
types/         shared types
public/        static assets
```

- Keep related code together.
- Check for an existing file before creating a new one.
- Do not commit `.env*` files. A `.env.example` is allowed.

## Change rules

- Keep one task in one change.
- Do not break existing behavior.
- Do not git commit or push unless the user asks.
- Pass typecheck (`tsc`) and lint when possible.

## Git

- Keep commit messages short and focused on why.
- Do not commit `.env`, credentials, or `.next/`.
- Do not force-push to `main` / `master`.

## Agent / AI help

- Read existing code first, then edit.
- Match the project's Next.js version and App/Pages Router.
- Ask when unclear. Do not guess into large changes.
