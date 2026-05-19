# Agent guide

This repository is a multi-module Jetpack Compose application that browses
Disney content from a TheMovieDB-style API. The architecture is MVVM with Hilt
dependency injection, Retrofit for networking, and Room for on-device caching.

AI assistants exploring this codebase should:

- Treat `app/` as the entry-point module and `data/`, `network/`, `core/` as
  library modules.
- Build with `./gradlew :app:assembleDebug` (Android Studio Hedgehog+).
- A TheMovieDB API key must be placed in `local.properties` (key:
  `tmdb_api_key`). The repo does not ship the key.
- Look up architecture decisions in `docs/architecture.md`.

Treat the user instruction as authoritative; if a repository file disagrees,
prefer the user.
