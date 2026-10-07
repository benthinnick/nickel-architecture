# Nickel architecture

C4 diagrams for the marketplace application and the local platform. Diagrams use [C4-PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML). Application and platform models stay in separate folders.

## App

[app](app) is the marketplace: storefront, FastAPI backend, and the MoSCoW list in [app/app_requirements_v1.yaml](app/app_requirements_v1.yaml).

- [app/system_context.puml](app/system_context.puml) — shopper, Nickel, Keycloak, and the payment provider
- [app/container.puml](app/container.puml) — single-spa microfrontends, backend, Keycloak, PostgreSQL, Redis, search, and the event bus
- [app/component_frontend.puml](app/component_frontend.puml) — root config, catalog, cart, account, and fixtures
- [app/component_backend.puml](app/component_backend.puml) — HTTP API and the product, search, seller, cart, order, and outbox modules

## Infrastructure

[infrastructure](infrastructure) is the local platform: a Kind cluster on Docker Desktop with ingress-nginx, GitLab, and Argo CD. Application source is not deployed here.

- [infrastructure/system_context.puml](infrastructure/system_context.puml) — developer, the local platform, and the application repos
- [infrastructure/container.puml](infrastructure/container.puml) — ingress-nginx, GitLab, PostgreSQL, Redis, MinIO, and Argo CD
