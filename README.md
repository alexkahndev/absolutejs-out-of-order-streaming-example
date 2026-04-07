# AbsoluteJS Out-of-Order Streaming Example

An example project demonstrating the [AbsoluteJS](https://absolutejs.com) out-of-order streaming model across React, Svelte, Vue, and Angular.

## What Is Out-of-Order Streaming?

Out-of-order streaming lets slow async sections stream as soon as they resolve instead of blocking everything above them in the response. Fast content arrives first, then slower stream slots patch in independently.

## What This Example Shows

- **Per-framework streaming pages** - A dedicated route for each framework that uses `StreamSlot`.
- **Fallback while waiting** - Async chunks render with placeholders while work is still pending.
- **Out-of-order delivery** - Streamed slots resolve independently and patch in by slot ID.
- **Cross-framework routing** - One backend plugin drives React, Svelte, Vue, Angular, HTML, and HTMX routes.
- **Shared structure/style** - The project layout matches the other `absolutejs-*` examples under `~/alex`.

## Prerequisites

- [Bun](https://bun.sh) (v1.1+)

## Getting Started

```bash
bun install
bun run dev
```

The server prints the local URL, usually `http://localhost:3000`.

## Scripts

| Command             | Description                           |
| ------------------- | ------------------------------------- |
| `bun run dev`       | Start the development server with HMR |
| `bun run start`     | Start the production server           |
| `bun run lint`      | Run ESLint                            |
| `bun run format`    | Format code with Prettier             |
| `bun run typecheck` | Run type checking across all frameworks |

## Project Structure

```
src/
├── backend/
│   ├── assets/              # Static assets (icons, images, SVGs)
│   ├── plugins/
│   │   └── pagesPlugin.ts   # Route definitions for each page
│   ├── server.ts            # Elysia server setup
│   └── vueImporter.ts       # Vue SSR import helper
└── frontend/
    ├── angular/             # Angular streaming page
    ├── html/                # Plain HTML reference page
    ├── htmx/                # HTMX reference page
    ├── react/               # React streaming page
    ├── styles/              # Shared styles
    ├── svelte/              # Svelte streaming page
    └── vue/                 # Vue streaming page
```

## Routes

| Path                | Framework | Description |
| ------------------- | --------- | ----------- |
| `/`                 | React     | React out-of-order streaming demo |
| `/react-streaming`  | React     | Alias for the React streaming demo |
| `/vue`              | Vue       | Vue out-of-order streaming demo |
| `/vue-streaming`    | Vue       | Alias for the Vue streaming demo |
| `/svelte`           | Svelte    | Svelte out-of-order streaming demo |
| `/svelte-streaming` | Svelte    | Alias for the Svelte streaming demo |
| `/angular`          | Angular   | Angular out-of-order streaming demo |
| `/angular-streaming`| Angular   | Alias for the Angular streaming demo |
| `/html`             | HTML      | Static reference page |
| `/htmx`             | HTMX      | Static reference page |
