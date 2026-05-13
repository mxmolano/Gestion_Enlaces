# Backlog Técnico Sprint 0 y Sprint 1

## Resumen
Crear desde cero una app local-first en monorepo con `backend/`, `frontend/` y `docker-compose.yml`. El primer entregable funcional será: abrir la app, pegar una URL, guardar con Enter o botón, y verla arriba en “Recientes” como `PENDING`, sin IA ni metadatos.

## Sprint 0 — Base Técnica
- Crear backend Spring Boot con Java 21, Maven, Spring Web, Spring Data JPA, Validation, PostgreSQL Driver y Flyway.
- Crear frontend Angular liviano, con pantalla inicial en el bundle principal y `apiBaseUrl` configurable.
- Crear `docker-compose.yml` con PostgreSQL local.
- Configurar CORS solo para desarrollo: Angular `http://localhost:4200` contra backend `http://localhost:8080`.
- Crear migración inicial Flyway para tabla `links` con: `id`, `url`, `title`, `description`, `notes`, `status`, `favorite`, `archived`, `created_at`, `updated_at`, `last_opened_at`.
- Agregar índices mínimos para `created_at`, `status`, `favorite` y `archived`.

## Sprint 1 — Captura Rápida
- Backend:
  - Implementar `POST /api/links/quick`.
  - Body: `{ "url": "example.com" }`.
  - Normalizar URL agregando `https://` si no tiene esquema.
  - Validar URL de forma simple; si es inválida, devolver error claro.
  - Crear enlace con `status=PENDING`, `favorite=false`, `archived=false`.
  - No llamar IA, metadatos, favicon ni procesos externos.
  - Implementar `GET /api/links/recent?limit=20`, ordenado por `createdAt desc`, excluyendo archivados por defecto.
- Frontend:
  - Crear pantalla inicial con campo “Pega un enlace…”, botón Guardar y lista de recientes.
  - Enter en el input ejecuta guardado rápido.
  - Al guardar correctamente: limpiar input, mostrar toast breve “Enlace guardado” y agregar el enlace arriba en recientes.
  - Si falla: mantener lo escrito y mostrar error simple.
  - Mostrar título si existe; si no, mostrar dominio o URL.
  - Mantener UI limpia, sin formulario completo en la primera pantalla.

## Interfaces Públicas
- `POST /api/links/quick`
  - Request: `{ "url": "https://example.com" }`
  - Response: `{ "id": 1, "url": "...", "title": null, "status": "PENDING", "favorite": false, "archived": false, "createdAt": "..." }`
- `GET /api/links/recent?limit=20`
  - Response: lista JSON de enlaces recientes no archivados.
- Enum inicial de estado: `PENDING`, `REVIEWED`, `READ`, `ARCHIVED`, `DISCARDED`.
- Duplicados: permitidos en Sprint 1 para no bloquear la captura rápida; detección/decisión queda para importación o fase posterior.

## Pruebas y Aceptación
- Backend:
  - Crear enlace con solo URL.
  - Completar `https://` cuando falte esquema.
  - Rechazar URL inválida con mensaje claro.
  - Confirmar que el enlace nace como `PENDING`.
  - Confirmar que `GET /recent` devuelve nuevos primero.
- Frontend:
  - Guardar con Enter.
  - Guardar con botón.
  - Input queda limpio tras éxito.
  - Input conserva valor tras error.
  - Enlace nuevo aparece arriba sin recargar la app.
- Manual:
  - Levantar PostgreSQL, backend y frontend localmente.
  - Abrir app, pegar URL, presionar Enter y verificar que queda guardada como pendiente en menos de una interacción visible.

## Supuestos
- Base de datos: PostgreSQL local con Docker.
- Backend: Spring Boot 3.x con Java 21 y Maven.
- Frontend: Angular generado con CLI, sin librería visual pesada en Sprint 1.
- La app no implementa IA, metadatos, etiquetas, búsqueda ni exportación en estos dos primeros sprints.
