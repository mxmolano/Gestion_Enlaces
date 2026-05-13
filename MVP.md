# 1. Cerrar el MVP exacto

Antes de programar, hay que definir qué entra en la primera versión y qué no.

El **MVP** debería ser solo esto:

```text
1. Abrir rápido la app.
2. Pegar una URL.
3. Guardar con Enter o botón.
4. Guardar aunque solo exista la URL.
5. Crear el enlace como Pendiente.
6. Ver enlaces recientes.
7. Buscar enlaces.
8. Editar enlace después.
9. Agregar etiquetas.
10. Marcar favorito.
11. Filtrar por etiqueta, favorito y pendiente.
12. Exportar datos.
```

Todo esto queda fuera por ahora:

```text
IA
Autocompletado
Resumen automático
Sincronización
Multiusuario
Extensión del navegador
Estadísticas avanzadas
```

La primera versión debe ser simple y rápida.

---

# 2. Definir la arquitectura base

Como quieres Angular + Java, la arquitectura inicial sería:

```text
gestion-enlaces/
│
├── backend/
│   └── Spring Boot
│
├── frontend/
│   └── Angular
│
└── docker-compose.yml
```

## Backend

```text
Java 21
Spring Boot
Spring Web
Spring Data JPA
Flyway
Base de datos local
```

Para la base de datos, recomiendo una de estas dos opciones:

## Opción simple

```text
SQLite
```

Buena para local, ligera y rápida.

## Opción más escalable

```text
PostgreSQL local
```

Mejor si después quieres convertir la app en servidor, multiusuario o sincronizada.

Mi recomendación para ti:

```text
PostgreSQL local con Docker
```

Porque empiezas local, pero no te limita después.

---

# 3. Definir el modelo de datos inicial

Para el MVP no necesitas muchas tablas.

Empieza con estas:

```text
links
tags
link_tags
```

## Tabla `links`

```text
id
url
title
description
notes
status
favorite
archived
created_at
updated_at
last_opened_at
```

## Tabla `tags`

```text
id
name
color
created_at
updated_at
```

## Tabla `link_tags`

```text
link_id
tag_id
```

Más adelante agregas:

```text
type
language
collection_id
priority
ai_status
ai_summary
```

Pero no lo metería todo al principio para no complicar el MVP.

---

# 4. Crear la primera historia técnica

La primera historia que deberías desarrollar es esta:

# HU-001 — Guardar enlace rápido

**Objetivo:** poder pegar una URL y guardarla inmediatamente.

## Backend

Crear este endpoint:

```text
POST /api/links/quick
```

Body:

```json
{
  "url": "https://example.com"
}
```

Respuesta:

```json
{
  "id": 1,
  "url": "https://example.com",
  "title": null,
  "status": "PENDING",
  "favorite": false,
  "archived": false,
  "createdAt": "2026-05-13T10:00:00"
}
```

Reglas:

```text
- Solo la URL es obligatoria.
- Si la URL no tiene https://, el backend puede completarla.
- El enlace queda como PENDING.
- No se llama IA.
- No se buscan metadatos.
- No se espera nada externo.
```

---

# 5. Crear la primera pantalla en Angular

La primera pantalla no debe ser compleja.

Debe tener esto:

```text
[ Pega un enlace aquí... ] [Guardar]

Recientes
- enlace 1
- enlace 2
- enlace 3
```

Flujo:

```text
1. El usuario pega una URL.
2. Presiona Enter.
3. Angular llama a POST /api/links/quick.
4. El enlace aparece arriba en recientes.
5. El input queda limpio.
6. La app muestra: "Enlace guardado".
```

Esta sería la primera victoria real del proyecto.

---

# 6. Orden de desarrollo recomendado

## Sprint 0 — Preparación

```text
1. Crear repositorio.
2. Crear backend Spring Boot.
3. Crear frontend Angular.
4. Configurar base de datos.
5. Configurar Flyway.
6. Crear docker-compose.
```

## Sprint 1 — Captura rápida

```text
1. Crear tabla links.
2. Crear entidad Link.
3. Crear endpoint POST /api/links/quick.
4. Crear endpoint GET /api/links/recent.
5. Crear pantalla inicial Angular.
6. Guardar con Enter.
7. Mostrar enlaces recientes.
```

## Sprint 2 — Edición básica

```text
1. Editar título.
2. Editar descripción.
3. Editar notas.
4. Cambiar estado.
5. Marcar favorito.
6. Archivar enlace.
```

## Sprint 3 — Etiquetas

```text
1. Crear tabla tags.
2. Crear tabla link_tags.
3. Crear etiquetas.
4. Asignar etiquetas a enlaces.
5. Filtrar por etiquetas.
```

## Sprint 4 — Búsqueda y filtros

```text
1. Buscar por URL.
2. Buscar por título.
3. Buscar por descripción.
4. Buscar por notas.
5. Filtrar pendientes.
6. Filtrar favoritos.
```

## Sprint 5 — Respaldo

```text
1. Exportar JSON.
2. Importar JSON.
3. Detectar duplicados.
```

---

# 7. El primer objetivo medible

El primer objetivo del proyecto debería ser este:

> En menos de una semana de desarrollo, poder abrir la app, pegar una URL, presionar Enter y verla guardada como pendiente.

Ese es el corazón de la aplicación.

Si eso se siente rápido, el proyecto va por buen camino.

---

# 8. El siguiente entregable recomendado

El siguiente documento que deberías tener es:

# Backlog técnico del MVP

Con tareas como estas:

```text
BACK-001 Crear proyecto Spring Boot
BACK-002 Configurar base de datos local
BACK-003 Crear migración de tabla links
BACK-004 Crear entidad Link
BACK-005 Crear repositorio LinkRepository
BACK-006 Crear servicio LinkService
BACK-007 Crear endpoint POST /api/links/quick
BACK-008 Crear endpoint GET /api/links/recent

FRONT-001 Crear proyecto Angular
FRONT-002 Crear layout principal
FRONT-003 Crear componente QuickSave
FRONT-004 Crear servicio LinkService
FRONT-005 Conectar POST /api/links/quick
FRONT-006 Mostrar confirmación de guardado
FRONT-007 Mostrar lista de recientes
FRONT-008 Guardar con Enter
```

---

# Mi recomendación concreta

El próximo paso debe ser:

> **Diseñar el backlog técnico del Sprint 0 y Sprint 1.**

No empezaría todavía con IA, etiquetas avanzadas ni pantallas complejas.

Primero hay que construir el núcleo:

```text
Guardar rápido.
Ver reciente.
Buscar después.
```

Ese es el corazón de tu app.
 
