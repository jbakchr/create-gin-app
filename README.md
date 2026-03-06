# create-gin-app

> The fast, opinionated way to scaffold production-ready **Gin** projects — with presets for layout, auth, DB, Swagger/OpenAPI, Docker & CI.

## Status

**Pre-release**. The first public CLI preview is in active development. Watch the repo to get notified when `v0.1.0` is out.

## Why?

Go’s Gin has great templates and examples, but there isn’t a modern, one-command **create-\* style** generator that:

- offers **layout presets** (Standard vs Clean Architecture),
- lets you toggle **features** (JWT auth, GORM + Postgres/MySQL/SQLite, Redis, CORS, request ID, logging),
- supports **spec-first** (OpenAPI → generated types/handlers) _or_ code-first,
- ships with **Makefile/Task**, **Docker Compose**, **hot reload**, **lint/CI** ready to go.

`create-gin-app` aims to be that “just works” starting point.

## Vision (MVP)

```text
create-gin-app my-api \
  --layout=standard|clean \
  --db=postgres|mysql|sqlite|none \
  --orm=gorm|none \
  --auth=jwt|none \
  --spec=oapi-codegen|go-gin-server|none \
  --docker --ci --hot-reload
```

## Generated project:

- cmd/ entrypoint, internal/ for app code (handlers/router/middleware/service/repository/model)
- sensible defaults (logging, CORS, request ID)
- optional OpenAPI workflows
- optional Docker + compose for DB/cache
- Make targets (make dev, make test, make generate, etc.)

## Install (coming soon)

Once the first release is cut:

```go
go install github.com/jbakchr/create-gin-app@latest
```

## Quick start (planned)

```bash
create-gin-app my-api --layout=clean --db=postgres --orm=gorm --auth=jwt --docker --ci
cd my-api
make dev
```

## Roadmap

- [ ] v0.1.0: Cobra CLI with new (one-shot generator), two presets (standard/clean), basic flags
- [ ] Spec-first option: OpenAPI via oapi-codegen or openapi-generator (user choice)
- [ ] --docker, --ci, --hot-reload switches
- [ ] Post-create generators: create-gin-app generate resource <name> --crud
- [ ] Docs site + examples

> If you have ideas or want to help, please open an issue with “Proposal:” in the title.

## License

MIT
