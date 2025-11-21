# AI Context: <your-app> Android App

<your-app> is an offline-first recipe management app built with Kotlin, Jetpack Compose, and Ktor.  
Users can save recipes, browse a library, generate weekly meal plans, and get grocery lists.

## Architectural Goals
- Kotlin-only codebase
- MVVM with Repository pattern
- Offline-first sync model
- Unidirectional Data Flow
- Local DB as SSOT
- Clear domain/data separation
- Stateless, preview-friendly Composables
- Scalable navigation graph
- Testability across all layers

## Tech Stack
< describe-your-tech-stack-here >
- UI: Jetpack Compose + Material3 + Jetpack Navigation
- DI: Hilt
- Async: Kotlin Coroutines + Flow + StateFlow
- Persistence: Room + TypeConverters
- Networking: Ktor + Kotlinx Serialization
- Logging: Timber + SLF4J/Logback
- Testing: JUnit + CoroutineTest + Turbine later

## Core Modules / Layers
-  We break our code into feature packages and a core package with code shared across features. 
- `data/` → Room, DAOs, DTOs, network service, repository impl
- `domain/` → Models & interfaces
- `ui/` → Compose screens, ViewModels, navigation
- `di/` → Hilt modules

## Current Key Features
- <your-features-here>

## 🔄 Sync and Data Layer Guidelines

<tune-this: depending on your architectural choices> 

- Local persistence uses SQLite via Room with FTS5 enabled.
- All entities use backend-generated UUIDv7 IDs (time-sortable).
- Do not create auto-increment IDs or entity prefixes.
- Sync is two-step:
    1. POST /sync/push uploads local outbox entries.
    2. GET /sync/pull?since=<timestamp> fetches backend deltas.
- Client tracks lastSyncedAt and syncState per entity.
- Always perform DB writes inside transactions and mark successful syncs as SYNCED.
- Conflicts resolved by last-writer-wins based on updatedAt.
- WorkManager runs sync on startup, connectivity, or local mutation events.


## Code Style Requirements
- Follow idiomatic Kotlin & Compose patterns
- ViewModels expose `StateFlow<UiState>` and handle logic
- UI screens are stateless + Previewable
- Repository interfaces in domain layer
- Always use dependency injection (Hilt)
- Persistence models separated from domain models
- Handle offline & error states gracefully
- Avoid unnecessary recompositions

## What AI Should Do
- Propose diffs, not full file rewrites
- Follow project patterns and libraries listed above
- Ask clarifying questions if context is missing
- Provide tests with new features when feasible
