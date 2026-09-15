# TestBear

**Test automation and CI/CD suite for the AI era.**

TestBear lets you record real browser interactions once and turn them into reliable, repeatable end-to-end tests — then run, automate, and orchestrate them through a visual CI/CD workflow editor.

## What it does

- **Record** — capture real user flows straight from the browser, no manual scripting
- **Edit** — review and refine each captured step before it becomes a test
- **Replay** — run flows across Chromium, Firefox, and WebKit on demand
- **Automate** — wire flows into CI/CD with a visual pipeline editor, so suites run automatically and stay in sync with your app

## Monorepo structure

This is a Next.js monorepo built with shadcn/ui.

```
apps/
  web/              # main Next.js app
packages/
  ui/               # shared component library (@testbear/ui)
```

## Getting started

```bash
pnpm install
pnpm dev
```

## Adding components

To add a shadcn/ui component, run the following from the root of the repo:

```bash
pnpm dlx shadcn@latest add button -c apps/web
```

This places the component source in `packages/ui/src/components`.

## Using components

Import shared components from the `@testbear/ui` package:

```tsx
import { Button } from "@testbear/ui/components/button";
```

## Tech stack

- Next.js + shadcn/ui
- pnpm workspaces
- Chrome extension (recorder) built on WXT, capturing DOM events and assembling multi-strategy CSS selectors into `@puppeteer/replay`-compatible JSON
- `puppeteer-core` (browser-safe build) with `ExtensionTransport` for zero-overhead CDP control during recording