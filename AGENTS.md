# AGENTS.md

## Project status

This project is in the **scaffolding/planning phase**. No source code, package manifests, build config, or CI exists yet. The only authoritative documents are the two listed below.

## Key documents

- `Contratos.md` — data models (Course, Class, Teacher) and API contracts (3 endpoints)
- `Backend/README.md` — architecture overview and technology choices

## Tech stack (from docs)

| Layer    | Tech                                      |
|----------|-------------------------------------------|
| Backend  | Python, FastAPI, PostgreSQL, Docker       |
| Frontend | TypeScript, CSS Modules, SASS             |
| iOS      | Swift, SwiftUI                            |
| Android  | Kotlin, Jetpack Compose                   |

## API (from Contratos.md)

- `GET /courses` — list all courses (summary view, no nested classes)
- `GET /courses/<slug>` — single course with nested classes and teacher list
- `GET /courses/<slug>/classes/<id>` — single class with full details

All responses include `id`, `created_at`, `updated_at`, and `deleted_at` (soft-delete pattern).

## Installed skills

- `fastapi-templates` (`.agents/skills/fastapi-templates/SKILL.md`) — FastAPI project scaffolding patterns (async, DI, repository/service layers, testing with pytest+httpx). Reference for project structure, NOT a drop-in: the contract uses **soft-delete** (`deleted_at`), not hard deletes. Adapt accordingly.

## Starting point

Nothing is implemented. The first step should be scaffolding the FastAPI backend under `Backend/`, setting up a package manager (`poetry` or `pip` + `requirements.txt`), and implementing the three endpoints defined in `Contratos.md`.
