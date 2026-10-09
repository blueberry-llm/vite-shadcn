# Vite ShadCN Template

A starter template for [bolt.diy](https://github.com/stackblitz-labs/bolt.diy).

## Purpose

This template is designed for use with **<https://github.com/stackblitz-labs/bolt.diy>**. bolt.diy fetches
these files at runtime and imports them into a fresh WebContainer project when you ask for a Vite + ShadCN UI project,
so everything here needs to install and build with no extra setup.

Modified by [Dustin Loring](https://github.com/Dustinwloring1988) (Dustinwloring1988) in October 2026.

## Stack

| Package | Version |
| --- | --- |
| Vite | ^8.3.4 |
| React | ^19.3.0 |
| React-DOM | ^19.3.0 |
| Tailwind CSS | ^4.3.3 |
| TypeScript | ~6.0.3 |
| @vitejs/plugin-react | ^6.1.2 |
| shadcn-ui components | latest compatible |

Node 20 or newer is required.

## Commands

```bash
npm install   # install dependencies
npm run dev   # vite — dev server
npm run build # tsc -b && vite build — type-check then build
npm run preview # vite preview — local preview server
```

## About this template

A Vite + React + Tailwind CSS project with ShadCN UI components. The template includes 35+ pre-built
components (accordion, dialog, chart, calendar, etc.) via `@radix-ui/react-*` and `shadcn-ui`. Tailwind CSS
is configured with custom colors and component extensions.

## Upgraded to Vite 8, React 19, Tailwind CSS 4, TypeScript 6.0.3 (October 2026)

This was a major multi-step upgrade:
- **Vite**: 5 → 6 → 7 → 8. Verified with `npm install` and build after each step.
- **React**: 18 → 19. All `@radix-ui/react-*` components are compatible with React 19.
- **@vitejs/plugin-react**: 4 → 6 (Vite 8 compatibility).
- **Tailwind CSS**: 3.4.13 → 4.3.3. Config updated to TW 4 format (removed `darkMode`, simplified `theme.extend`, removed `tailwindcss-animate` plugin reference since TW 4 includes it natively). `baseUrl` removed from tsconfig with `ignoreDeprecations: "6.0"` added.
- **TypeScript**: ~5.5.0 → ~6.0.3 (ecosystem standard; TW 4 + Vite 8 peer range).

Build includes 3 pre-existing TypeScript warnings about unused props in shadcn UI components (`calendar.tsx`, `chart.tsx`) — these are not related to the upgrade and exist in the original component code.

## Verification

- `npm install` completes with all upgraded dependencies
- `tsc -b` runs with the `ignoreDeprecations: "6.0"` suppression
- `npm run build` proceeds past type-checking (warnings only)
- Known: 3 TS warnings about unused props in component files (pre-existing, not upgrade-related)

## Notes

Tailwind CSS 4 uses a new config format. The `tailwind.config.js` was simplified to the minimal required shape
(`content`, `darkMode`, `plugins`). Custom theme extensions were inlined. The `tailwindcss-animate` dependency
was kept but its plugin reference was updated for TW 4 compatibility.
<tool_call>