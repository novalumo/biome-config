# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a shared Biome configuration package (`@novalumo/biome-config`) distributed via npm. The main export is `biome.json` which contains formatting, linting, and assist rules for JavaScript, TypeScript, CSS, HTML, and JSON files.

## Package Manager

Use `bun` as the package manager throughout the project (not npm).

## Common Commands

### Development
- Install dependencies: `bun install`
- Lint and format with Biome: `bunx biome check --write .`

### Release Process

This project uses [changesets](https://github.com/changesets/changesets) for automated releases via GitHub Actions.

**Standard workflow:**
1. Create a changeset: `bun run changeset`
2. Commit the changeset file (`.changeset/*.md`) and create a PR
3. Merge the PR to main
4. GitHub Actions automatically creates a "Version Packages" PR
5. Merge the Version Packages PR to trigger automatic npm publishing

**Available commands:**
- Create changeset: `bun run changeset`
- Update versions: `bun run version` (usually done automatically by GitHub Actions)
- Publish: `bun run release` (usually done automatically by GitHub Actions)
- Manual publish: `npm publish` (not recommended; only use if automated process fails)

## Configuration Details

The main configuration file is `biome.json` which:
- Uses 2-space indentation and line width of 80
- Enables formatting, linting, and assist features for JS/TS, CSS, HTML, and JSON
- Excludes common build/cache directories (.next, .vercel, dist, node_modules, etc.)
- Has specific linting rules for accessibility, security, and code quality
- Disables VCS integration (git hooks)
