# Architecture overview

`app/` (the application module) depends on the library modules below in a
strict, non-cyclic way.

## Module diagram

```
app  ->  ui  ->  domain  ->  data  ->  network
                                   ->  database (Room)
                                   ->  core
```

## Layer responsibilities

- **ui**: Compose screens, state holders, ViewModels.
- **domain**: pure-Kotlin use cases, no Android dependencies.
- **data**: repositories that combine network + database. Single source of truth
  per content type (films, characters).
- **network**: Retrofit services + OkHttp client.
- **database**: Room entities, DAOs, type converters.
- **core**: dispatcher providers, common utilities, no business logic.

## Concurrency

All repositories expose `suspend` functions or `Flow<T>`. The single
`OkHttpClient` is shared via Hilt; it is thread-safe by construction. The Room
database is created once per process via `@Singleton` provider.
