# Project Context

## Purpose
**True Valence Mapper (OpenSpec Edition)** is a React 18 + TypeScript application for visualizing relationship patterns. This edition focuses on integrating **OpenSpec** to enable AI-assisted specification generation, validation, and multi-agent collaboration.

## Tech Stack
- **Core**: React 18, TypeScript
- **Build**: Vite
- **Styling**: Tailwind CSS
- **State/Backend**: Supabase (shared schemas)
- **Tools**: OpenSpec v0.16.0, Node.js

## Project Conventions

### Code Style
- **TypeScript**: Strict mode enabled.
- **Components**: Functional components with hooks only. No class components.
- **Exports**: Named exports preferred (`export function Component()`).
- **Styling**: Tailwind CSS utility classes.

### Architecture Patterns
- **Multi-Repo**: This is one edition in a polyrepo architecture.
- **Shared Assets**: Reusable code resides in the parent repo's `shared/` directory.
- **Submodules**: Changes here trigger updates in the parent repository.

### Testing Strategy
- **Unit**: Jest + React Testing Library (`*.test.tsx`).
- **Specs**: OpenSpec for requirement verification and "spec-driven" validation.

### Git Workflow
- **Branching**: Feature branches from `main`.
- **Commits**: Conventional Commits (`type: description`).
- **Sync**: Pushes to `main` trigger parent repo sync.

## Domain Context
The domain is **Relationship Mapping**.
- **Entities**: People, Organizations.
- **Relationships**: Valence (quality/nature of connection), Roles, Dates.
- **Goal**: Visualize complex ecosystem maps to reveal hidden patterns.

## Important Constraints
- **Governance**: Do NOT add new npm packages without human approval (see root `AGENTS.md`).
- **Dependencies**: Check `shared/` before creating new utilities.

## External Dependencies
- **Parent Repo**: `rhart696/true-valence-mapper`
- **Supabase**: Authentication and Data Persistence.
