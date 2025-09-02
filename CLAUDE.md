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

### Publishing
- Publish to npm: `npm publish` (uses npm for publishing as configured in package.json)

## Configuration Details

The main configuration file is `biome.json` which:
- Uses 2-space indentation and line width of 80
- Enables formatting, linting, and assist features for JS/TS, CSS, HTML, and JSON
- Excludes common build/cache directories (.next, .vercel, dist, node_modules, etc.)
- Has specific linting rules for accessibility, security, and code quality
- Disables VCS integration (git hooks)
