# Technology strategy

Use the simplest maintainable stack that matches each project's users and
problem. JavaScript with browser APIs is appropriate for AlgorithmUniverse;
its first milestone has no server, database, or third-party dependencies.

## Defaults

- Relational applications: PostgreSQL, with versioned migrations and explicit
  constraints. Use SQLite for embedded/local tools.
- HTTP contracts: REST with OpenAPI where an API is a real product boundary.
- UI: React, Angular, Vue, Compose, or SwiftUI only where their ecosystem adds
  clear value; static HTML/CSS/JS is preferred for small self-contained tools.
- Containers and orchestration: Docker Compose for reproducible multi-service
  development. Kubernetes only when deployment requirements justify it.
- Observability: structured logs first; add OpenTelemetry, Prometheus, or
  Grafana for services that need them.
- Security: established authentication and cryptographic libraries, least
  privilege, validated inputs, and synthetic sample data.
- CI: GitHub Actions with reproducible language-native builds, tests, and
  dependency checks. Use remote runners for Android-hostile builds.

## Toolchain matrix

Each project records exact toolchain versions and formatter, linter, test, and
dependency commands in its own README and CI workflow. Avoid a portfolio-wide
framework mandate that makes projects harder to build.
