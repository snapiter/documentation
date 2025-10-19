# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Docusaurus-based documentation website** for Snapiter. It serves technical documentation for a self-hosted service, as well as links to hosted instances. The site is built with Docusaurus 3.9.2, React 19, TypeScript, and uses Node 20+.

## Common Development Commands

### Setup
```bash
npm install
# or
yarn
```

### Local Development
```bash
npm start
# or
yarn start
```
Starts a development server on `http://localhost:3000` with hot reload. Changes are reflected live without restarting.

### Build
```bash
npm run build
# or
yarn build
```
Generates static content into the `build/` directory. This is used for production deployments.

### Type Checking
```bash
npm run typecheck
# or
yarn typecheck
```
Runs TypeScript compiler to check for type errors without building.

### Serve Built Site
```bash
npm run serve
# or
yarn serve
```
Locally serves the built static site from the `build/` directory for testing production builds.

### Clear Cache
```bash
npm run clear
# or
yarn clear
```
Clears Docusaurus cache in `.docusaurus/` directory if you encounter build issues.

## Code Architecture

### Project Structure

```
documentation/
├── docs/                      # Main documentation content
│   ├── overview/             # Overview section (quick-start, snapiter.mdx)
│   ├── features/             # Feature documentation (trackables, trips, markers, devices)
│   └── install/              # Installation guides (requirements, docker-compose)
├── src/
│   ├── components/           # React components (HomepageFeatures)
│   ├── css/                  # Global and module styles
│   └── pages/                # Custom pages (index.tsx)
├── blog/                     # Blog posts (currently disabled)
├── static/                   # Static assets
├── docusaurus.config.ts      # Main Docusaurus configuration
├── sidebars.ts               # Sidebar navigation structure
└── package.json              # Dependencies and scripts
```

### Content Organization

- **Sidebar Navigation**: Configured in `sidebars.ts` with auto-generation from the `docs/` directory structure
- **Categories**: Each folder in `docs/` has a `_category_.json` file defining the folder's display properties
- **MDX Support**: Documentation uses `.mdx` files, allowing React components within Markdown

### Configuration

- **Site Config** (`docusaurus.config.ts`):
  - Title: "Snapiter"
  - Base URL: `/` (hosted at `https://docs.snapiter.com`)
  - Uses Docusaurus Classic preset
  - GitHub integration enabled for "edit this page" links
  - Prism themes: GitHub (light) and Dracula (dark)
  - Future v4 mode enabled for Docusaurus v4 compatibility

- **TypeScript**: Uses Docusaurus TypeScript config with base URL set to `.`

## Important Notes

- **Blog Disabled**: Blog functionality is currently disabled in the config (`blog: false`)
- **Edit Links**: "Edit this page" links point to the GitHub repository at `https://github.com/snapiter/documentation/tree/main/`
- **Node Version**: Requires Node.js 20.0 or later
- **Broken Links**: Set to throw errors (`onBrokenLinks: 'throw'`) to catch broken documentation links during build
- **Internationalization**: Currently English-only (`i18n: {defaultLocale: 'en', locales: ['en']}`)

## Documentation Content Areas

- **Overview**: Quick-start guides and Snapiter product overview
- **Features**: Trackables, Trips, Markers, Devices documentation
- **Install**: Requirements and Docker Compose deployment guides
