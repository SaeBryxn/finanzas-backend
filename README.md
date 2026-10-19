# CreditApp — API

Back end del simulador de crédito inmobiliario **CreditApp**. Guarda clientes, unidades inmobiliarias, configuraciones de crédito, simulaciones y un registro de auditoría.

**Stack:** .NET 8 · ASP.NET Core Minimal API · Entity Framework Core · PostgreSQL · Swagger · Docker

## Endpoints

Todos bajo `/api`:

| Recurso | Rutas | Descripción |
|---------|-------|-------------|
| `clients` | `GET` · `GET /{id}` · `POST` · `PUT /{id}` · `DELETE /{id}` | Clientes |
| `units` | `GET` · `GET /{id}` · `POST` · `PUT /{id}` · `DELETE /{id}` | Unidades: proyecto, torre, precio, cuota inicial, gastos y seguros |
| `configs` | `GET` · `POST` · `PUT /{id}` · `DELETE /{id}` | Parámetros del crédito |
| `simulations` | `GET` · `POST` · `DELETE /{id}` | Simulaciones guardadas |
| `audit` | `GET` · `POST` | Registro de acciones |

Además, `GET /health` para comprobar que la API está activa.

## Cómo ejecutarlo

Requisitos: .NET 8 SDK y PostgreSQL.

```bash
export ConnectionStrings__Default="Host=localhost;Port=5432;Database=creditapp;Username=postgres;Password=<tu-contraseña>"
dotnet run --project CreditApp.Api
```

Las migraciones se aplican al arrancar. Swagger queda disponible en `/swagger` en desarrollo. Incluye `Dockerfile`.

## Repositorios relacionados

- [finanzas-frontend](https://github.com/SaeBryxn/finanzas-frontend) — simulador en Vue 3 + TypeScript

---

Desarrollado por [Bryan Espejo](https://bryanespejo.pages.dev) · Ingeniería de Software, UPC
