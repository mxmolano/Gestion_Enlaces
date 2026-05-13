# 1. Visión del producto

Crear una aplicación para guardar enlaces de forma **muy rápida, simple e intuitiva**, principalmente local, hecha con **Angular + Java**, donde el usuario pueda capturar un enlace en segundos y organizarlo después.

La app debe servir para este caso real:

```text
Estoy viendo algo interesante.
No quiero distraerme.
No quiero llenar un formulario largo.
No quiero esperar a que cargue una IA.
Solo quiero pegar el enlace, guardarlo y seguir.
```

Por eso, la regla principal será:

> **Guardar primero, organizar después.**

---

# 2. Frase guía del producto

Esta frase debe guiar todas las decisiones:

> **La aplicación debe permitirme guardar un enlace antes de perder el interés, el foco o la paciencia.**

Si una funcionalidad hace que guardar un enlace sea más lento, esa funcionalidad no debe estar en el flujo principal.

---

# 3. Problema que resuelve

Muchas veces uno encuentra enlaces útiles, pero no los guarda porque:

* La app tarda en abrir.
* El formulario tiene demasiados campos.
* Hay que pensar mucho antes de guardar.
* La app espera a cargar información externa.
* La app intenta hacer demasiadas cosas al inicio.
* La IA o los metadatos tardan.
* El usuario pierde el interés o el foco.

Entonces esta app debe evitar eso.

---

# 4. Objetivo principal

El objetivo principal no es tener muchos campos.

El objetivo principal es:

```text
Abrir rápido.
Pegar enlace.
Guardar.
Seguir trabajando.
Organizar después.
```

---

# 5. Concepto central: captura rápida

La app debe tener un modo principal llamado mentalmente:

```text
Captura rápida
```

Este modo permite guardar un enlace con solo:

```text
URL
```

Nada más debe ser obligatorio.

Después, cuando el usuario tenga tiempo, puede completar:

```text
Título
Descripción
Tipo
Etiquetas
Idioma
Notas
Colección
Prioridad
Estado
Favorito
```

---

# 6. Reglas principales de la app

## Regla 1: Solo la URL es obligatoria

Para guardar un enlace, el usuario solo debe necesitar una URL.

```text
Campo obligatorio:
- URL

Campos opcionales:
- Título
- Descripción
- Tipo
- Etiquetas
- Idioma
- Notas
- Colección
- Prioridad
- Estado
- Favorito
```

---

## Regla 2: La app nunca debe esperar a la IA para guardar

Incorrecto:

```text
Pego un enlace.
La app consulta IA.
La app intenta generar título.
La app intenta generar etiquetas.
La app se demora.
Pierdo el foco.
```

Correcto:

```text
Pego un enlace.
La app guarda inmediatamente.
La IA puede trabajar después.
Yo sigo con lo mío.
```

---

## Regla 3: El formulario largo no debe aparecer primero

La app debe mostrar primero un formulario mínimo:

```text
URL
Guardar
```

Opcionalmente:

```text
Título
Etiquetas
```

Todo lo demás debe estar oculto en “Más opciones” o en la pantalla de edición.

---

## Regla 4: Guardar debe sentirse inmediato

Al guardar, la app debe responder rápido.

Idealmente:

```text
Guardar enlace en local: menos de 500 ms
```

Incluso si después hay procesos pendientes, el enlace ya debe quedar guardado.

---

## Regla 5: La app debe abrir rápido

La app debe mostrar algo útil rápidamente.

Objetivo recomendado:

```text
Pantalla visible: menos de 2 segundos
App usable: menos de 3 segundos
```

Debe cargar primero lo esencial:

```text
Buscador
Botón de guardar enlace
Enlaces recientes
```

Y después cargar lo secundario:

```text
Filtros avanzados
Estadísticas
Configuraciones
Procesos de IA
```

---

# 7. Prioridades del producto

## P0 — Obligatorio para el MVP

Esto es lo más importante:

1. Abrir rápido.
2. Guardar enlace con solo URL.
3. No bloquear el guardado por campos opcionales.
4. No bloquear el guardado por IA.
5. Guardar enlaces incompletos.
6. Mostrar enlaces recientes.
7. Buscar rápido.
8. Editar manualmente después.
9. Usar etiquetas fácilmente.
10. Funcionar localmente.
11. Tener una interfaz limpia.
12. Poder exportar datos.

---

## P1 — Importante después del MVP básico

1. Tipo de enlace.
2. Idioma.
3. Estados: pendiente, revisado, leído, archivado.
4. Colecciones.
5. Filtros avanzados.
6. Importación.
7. Atajos de teclado.
8. Modo oscuro.
9. PWA o app instalable.
10. Backups manuales.

---

## P2 — Futuro con IA

1. Sugerir título.
2. Sugerir descripción.
3. Sugerir etiquetas.
4. Detectar idioma.
5. Detectar tipo de contenido.
6. Generar resumen.
7. Detectar duplicados inteligentes.
8. Organizar enlaces automáticamente.
9. Procesar enlaces en segundo plano.
10. Sugerir colecciones.

---

# 8. Flujo ideal de uso

## Flujo principal: guardar sin perder el foco

```text
1. Abro la app.
2. Pego el enlace.
3. Presiono Enter o clic en Guardar.
4. La app confirma que se guardó.
5. Sigo con lo que estaba haciendo.
```

No debería obligarme a:

```text
Elegir tipo
Escribir descripción
Crear etiquetas
Esperar IA
Esperar metadatos
Entrar a otra pantalla
```

---

## Flujo secundario: organizar después

```text
1. Entro a enlaces pendientes.
2. Abro un enlace guardado rápidamente.
3. Agrego título, descripción, tipo, etiquetas e idioma.
4. Lo marco como revisado.
```

---

# 9. Estados del enlace

Como muchos enlaces se guardarán rápido, algunos estarán incompletos. Eso está bien.

Estados sugeridos:

```text
Pendiente
Revisado
Leído
Favorito
Archivado
Descartado
```

## Estado inicial recomendado

Cuando guardo un enlace rápido, debería quedar como:

```text
Pendiente
```

Así después puedo revisar todos los enlaces que guardé sin organizar.

---

# 10. Campos del enlace

## Campos mínimos

```text
id
url
createdAt
updatedAt
status
```

## Campos manuales

```text
title
description
type
language
notes
favorite
archived
priority
collectionId
```

## Campos para IA futura

```text
aiProcessed
aiStatus
aiSuggestedTitle
aiSuggestedDescription
aiSuggestedType
aiSuggestedLanguage
aiSuggestedTags
aiSummary
aiProcessedAt
```

## Campos técnicos útiles

```text
metadataStatus
metadataFetchedAt
lastOpenedAt
source
saveMode
```

Ejemplo de `saveMode`:

```text
QUICK
MANUAL
AI_ASSISTED
IMPORTED
```

---

# 11. Tipos de enlace sugeridos

Inicialmente pueden ser manuales.

```text
Artículo
Video
Documentación
Repositorio
Herramienta
Curso
Libro
Noticia
Blog
Podcast
Imagen
PDF
Otro
```

En el futuro, la IA puede sugerir el tipo automáticamente.

---

# 12. Idiomas sugeridos

```text
Español
Inglés
Portugués
Francés
Alemán
Italiano
Otro
Sin definir
```

En el guardado rápido, el idioma puede quedar como:

```text
Sin definir
```

---

# 13. Pantallas principales

## 13.1 Pantalla de inicio

Debe ser la pantalla más importante.

Debe mostrar:

```text
Barra para pegar enlace rápido
Buscador
Enlaces recientes
Botón de nuevo enlace
Filtros básicos
```

Ejemplo:

```text
------------------------------------------------
Pega un enlace y presiona Enter...
[ https://example.com/articulo ] [Guardar]
------------------------------------------------

Buscar enlaces...
[ angular, java, ia, documentación... ]

Recientes

⭐ Angular Signals explicado
   https://...
   #angular #frontend
   Pendiente

☆ Spring Boot Security Guide
   https://...
   #java #backend
   Revisado
```

---

## 13.2 Modal de guardado rápido

Debe ser pequeño y no intimidante.

```text
Guardar enlace

URL *
[________________________________]

Título opcional
[________________________________]

Etiquetas opcionales
[ frontend ] [ java ] [+ nueva]

[Guardar]
[Más opciones]
```

---

## 13.3 Formulario completo

Este formulario no debe ser el primero que aparece.
Debe usarse para editar después.

```text
URL
Título
Descripción
Tipo
Idioma
Etiquetas
Notas
Colección
Prioridad
Estado
Favorito
Archivado
```

---

## 13.4 Vista de pendientes

Muy importante para tu flujo.

Debe mostrar todos los enlaces guardados rápido que todavía no organizaste.

```text
Pendientes por organizar

- enlace 1
- enlace 2
- enlace 3
```

Acciones rápidas:

```text
Editar
Marcar como revisado
Agregar etiqueta
Eliminar
Abrir
```

---

## 13.5 Configuración

Debe permitir:

```text
Exportar datos
Importar datos
Configurar backups
Activar modo oscuro
Ver ubicación de datos locales
Configurar IA futura
```

---

# 14. Historias de usuario reestructuradas

A continuación van las historias ya reorganizadas según la prioridad real de la app.

---

# Épica A — Captura rápida sin perder el foco

Esta es la épica más importante.

---

## HU-001 — Abrir la aplicación rápidamente

**Como usuario**, quiero que la aplicación abra rápido, para poder guardar un enlace antes de perder el foco.

**Criterios de aceptación:**

* La pantalla principal debe mostrarse rápidamente.
* La app debe mostrar primero el campo para guardar enlace.
* La app no debe cargar procesos pesados al inicio.
* La app no debe iniciar IA automáticamente al abrir.
* Los datos secundarios pueden cargarse después.
* Si hay muchos enlaces, debe cargar primero los recientes.

**Prioridad:** P0
**Fase:** MVP

---

## HU-002 — Guardar enlace con solo URL

**Como usuario**, quiero guardar un enlace ingresando solo la URL, para no perder tiempo llenando datos.

**Criterios de aceptación:**

* El único campo obligatorio debe ser la URL.
* El sistema debe permitir guardar aunque no haya título.
* El sistema debe permitir guardar aunque no haya descripción.
* El sistema debe permitir guardar aunque no haya etiquetas.
* El sistema debe permitir guardar aunque no haya tipo ni idioma.
* El enlace debe guardarse inmediatamente.
* El enlace debe aparecer en la lista de recientes.

**Prioridad:** P0
**Fase:** MVP

---

## HU-003 — Guardar con Enter

**Como usuario**, quiero pegar un enlace y presionar Enter para guardarlo, para capturarlo sin interrumpirme.

**Criterios de aceptación:**

* Debe existir un campo rápido para pegar URL.
* Al presionar Enter, el enlace se guarda.
* Si la URL es válida, se confirma el guardado.
* Si la URL parece incompleta, el sistema puede intentar agregar `https://`.
* Si la URL es inválida, debe mostrar un error simple.
* El campo debe quedar listo para pegar otro enlace.

**Prioridad:** P0
**Fase:** MVP

---

## HU-004 — Guardado inmediato sin esperar metadatos

**Como usuario**, quiero que el enlace se guarde sin esperar título, descripción o favicon, para no perder el foco.

**Criterios de aceptación:**

* El sistema no debe bloquear el guardado intentando leer la página.
* La obtención de metadatos debe ser opcional.
* Si se implementa extracción de metadatos, debe ejecutarse después del guardado.
* Si falla la extracción, el enlace debe seguir guardado.
* El usuario debe poder completar los datos manualmente.

**Prioridad:** P0
**Fase:** MVP

---

## HU-005 — Guardado inmediato sin esperar IA

**Como usuario**, quiero que la IA nunca retrase el guardado de un enlace, para que la app siga siendo rápida.

**Criterios de aceptación:**

* La IA no debe ejecutarse antes de guardar.
* El botón Guardar no debe esperar una respuesta de IA.
* La IA debe ejecutarse después, si el usuario lo desea.
* Si la IA falla, el enlace no debe perderse.
* La app debe funcionar completamente sin IA.

**Prioridad:** P0
**Fase:** MVP con preparación para futuro

---

## HU-006 — Crear enlace como pendiente

**Como usuario**, quiero que los enlaces guardados rápidamente queden como pendientes, para organizarlos después.

**Criterios de aceptación:**

* Todo enlace guardado solo con URL puede quedar en estado `Pendiente`.
* Debe existir una vista de enlaces pendientes.
* El usuario debe poder cambiar el estado a `Revisado`.
* El usuario debe poder filtrar por pendientes.
* El estado debe guardarse en base de datos.

**Prioridad:** P0
**Fase:** MVP

---

## HU-007 — Confirmación rápida de guardado

**Como usuario**, quiero recibir una confirmación breve cuando guardo un enlace, para saber que funcionó sin que me interrumpa.

**Criterios de aceptación:**

* Después de guardar debe aparecer un mensaje corto.
* El mensaje no debe bloquear la pantalla.
* Ejemplo: `Enlace guardado`.
* Si ocurre error, debe explicarse de forma simple.
* El formulario no debe borrar los datos si falla el guardado.

**Prioridad:** P0
**Fase:** MVP

---

# Épica B — Edición manual después de guardar

---

## HU-008 — Editar enlace manualmente

**Como usuario**, quiero editar la información de un enlace después de guardarlo, para organizarlo cuando tenga tiempo.

**Criterios de aceptación:**

* El usuario puede editar URL.
* El usuario puede editar título.
* El usuario puede editar descripción.
* El usuario puede editar tipo.
* El usuario puede editar idioma.
* El usuario puede editar etiquetas.
* El usuario puede editar notas.
* El usuario puede guardar cambios sin recargar la app.

**Prioridad:** P0
**Fase:** MVP

---

## HU-009 — Agregar título manual

**Como usuario**, quiero escribir un título manualmente, para reconocer mejor el enlace.

**Criterios de aceptación:**

* El título debe ser opcional.
* El usuario puede dejarlo vacío.
* El usuario puede modificarlo después.
* El título debe mostrarse en la lista si existe.
* Si no hay título, la app puede mostrar la URL o el dominio.

**Prioridad:** P0
**Fase:** MVP

---

## HU-010 — Agregar descripción manual

**Como usuario**, quiero escribir una descripción del enlace, para recordar por qué lo guardé.

**Criterios de aceptación:**

* La descripción debe ser opcional.
* El usuario puede editarla después.
* La descripción puede mostrarse parcialmente en la lista.
* La descripción debe buscarse desde el buscador.

**Prioridad:** P1
**Fase:** MVP o Fase 2

---

## HU-011 — Agregar notas personales

**Como usuario**, quiero agregar notas personales a un enlace, para guardar mi propio contexto.

**Criterios de aceptación:**

* Las notas deben ser opcionales.
* Las notas pueden ser más largas que la descripción.
* Las notas deben guardarse localmente.
* Las notas deben poder buscarse.
* La IA futura no debe sobrescribir mis notas.

**Prioridad:** P1
**Fase:** Fase 2

---

# Épica C — Organización simple

---

## HU-012 — Crear etiquetas rápidamente

**Como usuario**, quiero crear etiquetas fácilmente, para organizar enlaces sin complicarme.

**Criterios de aceptación:**

* El usuario puede escribir una etiqueta y crearla.
* El sistema debe evitar etiquetas duplicadas exactas.
* El sistema puede sugerir etiquetas existentes.
* Las etiquetas deben poder asignarse a varios enlaces.
* Un enlace puede tener varias etiquetas.

**Prioridad:** P0
**Fase:** MVP

---

## HU-013 — Asignar etiquetas al guardar o editar

**Como usuario**, quiero agregar etiquetas al enlace si quiero, pero sin que sea obligatorio.

**Criterios de aceptación:**

* El campo de etiquetas debe ser opcional.
* El usuario puede agregar etiquetas durante el guardado rápido.
* El usuario puede agregar etiquetas después.
* El usuario puede quitar etiquetas.
* La app debe mostrar etiquetas en la lista.

**Prioridad:** P0
**Fase:** MVP

---

## HU-014 — Clasificar por tipo de contenido

**Como usuario**, quiero asignar un tipo al enlace, para saber qué clase de recurso guardé.

**Tipos iniciales:**

```text
Artículo
Video
Documentación
Repositorio
Herramienta
Curso
Libro
Noticia
Blog
Podcast
PDF
Otro
```

**Criterios de aceptación:**

* El tipo debe ser opcional.
* El usuario puede seleccionar un tipo.
* El usuario puede cambiarlo después.
* Debe existir filtro por tipo.
* En el futuro, la IA podrá sugerir el tipo.

**Prioridad:** P1
**Fase:** Fase 2

---

## HU-015 — Definir idioma del enlace

**Como usuario**, quiero indicar el idioma del enlace, para encontrar contenido por idioma.

**Criterios de aceptación:**

* El idioma debe ser opcional.
* El usuario puede seleccionar idioma.
* Debe existir la opción `Sin definir`.
* Debe existir filtro por idioma.
* En el futuro, la IA podrá detectar el idioma.

**Prioridad:** P1
**Fase:** Fase 2

---

## HU-016 — Marcar como favorito

**Como usuario**, quiero marcar enlaces importantes como favoritos, para encontrarlos rápido.

**Criterios de aceptación:**

* El usuario puede marcar o desmarcar favorito.
* El favorito debe poder cambiarse desde la lista.
* Debe existir filtro de favoritos.
* El estado debe persistir al reiniciar la app.

**Prioridad:** P0
**Fase:** MVP

---

## HU-017 — Cambiar estado del enlace

**Como usuario**, quiero cambiar el estado de un enlace, para saber si está pendiente, revisado o archivado.

**Estados sugeridos:**

```text
Pendiente
Revisado
Leído
Archivado
Descartado
```

**Criterios de aceptación:**

* El usuario puede cambiar el estado.
* Debe existir filtro por estado.
* Los enlaces guardados rápidamente pueden iniciar como `Pendiente`.
* Los archivados no deben aparecer por defecto en la lista principal.

**Prioridad:** P1
**Fase:** MVP o Fase 2

---

## HU-018 — Crear colecciones

**Como usuario**, quiero agrupar enlaces en colecciones, para organizar temas grandes.

**Criterios de aceptación:**

* El usuario puede crear una colección.
* Un enlace puede pertenecer a una colección.
* La colección debe ser opcional.
* Debe existir filtro por colección.
* Eliminar una colección no debe eliminar automáticamente los enlaces.

**Prioridad:** P1
**Fase:** Fase 2

---

# Épica D — Encontrar enlaces rápido

---

## HU-019 — Ver enlaces recientes al abrir

**Como usuario**, quiero ver primero mis enlaces recientes, para recuperar rápido lo último que guardé.

**Criterios de aceptación:**

* La pantalla inicial debe mostrar enlaces recientes.
* Los enlaces más nuevos deben aparecer arriba.
* Debe cargarse rápido.
* Desde la lista se debe poder abrir, editar, marcar favorito o archivar.
* No debe requerir entrar a varias pantallas.

**Prioridad:** P0
**Fase:** MVP

---

## HU-020 — Búsqueda instantánea

**Como usuario**, quiero buscar mientras escribo, para encontrar enlaces sin perder tiempo.

**Criterios de aceptación:**

* Debe existir una barra de búsqueda visible.
* La búsqueda debe responder rápido.
* Debe buscar por URL.
* Debe buscar por título.
* Debe buscar por descripción.
* Debe buscar por notas.
* Debe buscar por etiquetas.
* No debe congelar la interfaz.

**Prioridad:** P0
**Fase:** MVP

---

## HU-021 — Filtrar por etiquetas

**Como usuario**, quiero filtrar enlaces por etiquetas, para encontrar recursos de un tema específico.

**Criterios de aceptación:**

* El usuario puede seleccionar una o varias etiquetas.
* La lista debe actualizarse con el filtro.
* El usuario puede limpiar filtros.
* Los filtros deben poder combinarse con búsqueda.

**Prioridad:** P0
**Fase:** MVP

---

## HU-022 — Filtrar por tipo, idioma y estado

**Como usuario**, quiero filtrar por tipo, idioma y estado, para organizar mejor mis enlaces.

**Criterios de aceptación:**

* Debe existir filtro por tipo.
* Debe existir filtro por idioma.
* Debe existir filtro por estado.
* Los filtros deben poder combinarse.
* Los filtros avanzados pueden estar ocultos inicialmente para no saturar la pantalla.

**Prioridad:** P1
**Fase:** Fase 2

---

# Épica E — Interfaz intuitiva y sin estrés

---

## HU-023 — Pantalla inicial limpia

**Como usuario**, quiero una pantalla simple, para entender rápidamente qué hacer.

**Criterios de aceptación:**

* Debe verse claramente dónde pegar un enlace.
* Debe verse claramente dónde buscar.
* Debe haber pocos botones principales.
* Los filtros avanzados no deben ocupar demasiado espacio.
* La pantalla no debe sentirse saturada.

**Prioridad:** P0
**Fase:** MVP

---

## HU-024 — Formulario de dos niveles

**Como usuario**, quiero un formulario simple al inicio y opciones avanzadas solo si las necesito.

**Nivel simple:**

```text
URL
Título opcional
Etiquetas opcionales
Guardar
```

**Nivel avanzado:**

```text
Descripción
Tipo
Idioma
Notas
Colección
Prioridad
Estado
Favorito
Archivado
```

**Criterios de aceptación:**

* El formulario simple debe aparecer primero.
* Las opciones avanzadas deben estar ocultas o colapsadas.
* El usuario puede guardar sin abrir opciones avanzadas.
* El formulario no debe sentirse pesado.

**Prioridad:** P0
**Fase:** MVP

---

## HU-025 — Estado vacío útil

**Como usuario**, quiero que la app me guíe cuando no tengo enlaces, para saber cómo empezar.

**Criterios de aceptación:**

* Si no hay enlaces, debe mostrarse un mensaje claro.
* Debe haber un botón o campo para guardar el primer enlace.
* No debe parecer que la app está rota.
* El texto debe ser simple.

Ejemplo:

```text
Todavía no tienes enlaces guardados.
Pega tu primer enlace para empezar.
```

**Prioridad:** P0
**Fase:** MVP

---

## HU-026 — Atajos de teclado

**Como usuario avanzado**, quiero usar atajos de teclado, para guardar y buscar más rápido.

**Atajos sugeridos:**

```text
Ctrl + K: buscar
Ctrl + N: nuevo enlace
Ctrl + S: guardar
Esc: cerrar modal
Enter: guardar desde captura rápida
```

**Criterios de aceptación:**

* Los atajos principales deben funcionar.
* No deben interferir con acciones normales.
* Debe existir una pequeña ayuda visual.
* Deben ser opcionales, no obligatorios.

**Prioridad:** P1
**Fase:** Fase 2

---

# Épica F — Funcionamiento local y respaldo

---

## HU-027 — Funcionamiento local

**Como usuario**, quiero que la app funcione localmente, para no depender de internet.

**Criterios de aceptación:**

* La app debe poder ejecutarse en la máquina local.
* Los enlaces deben guardarse localmente.
* La búsqueda debe funcionar sin internet.
* La edición debe funcionar sin internet.
* La app no debe enviar datos externos sin autorización.

**Prioridad:** P0
**Fase:** MVP

---

## HU-028 — Consultar enlaces sin internet

**Como usuario**, quiero ver mis enlaces aunque no tenga internet, para acceder a mi biblioteca guardada.

**Criterios de aceptación:**

* La lista debe cargar sin internet.
* Los enlaces guardados deben poder buscarse sin internet.
* Los filtros deben funcionar sin internet.
* Solo abrir el enlace externo puede requerir internet.
* La IA futura puede requerir internet, pero no debe afectar lo local.

**Prioridad:** P0
**Fase:** MVP

---

## HU-029 — Exportar enlaces

**Como usuario**, quiero exportar mis enlaces, para tener respaldo de mi información.

**Criterios de aceptación:**

* El usuario puede exportar en JSON.
* Idealmente también en CSV.
* La exportación debe incluir URL, título, descripción, etiquetas, tipo, idioma, estado y fechas.
* El sistema debe mostrar confirmación al terminar.
* La exportación debe funcionar localmente.

**Prioridad:** P0
**Fase:** MVP

---

## HU-030 — Importar enlaces

**Como usuario**, quiero importar enlaces desde un archivo, para migrar o restaurar información.

**Criterios de aceptación:**

* El usuario puede importar JSON.
* El sistema debe validar el archivo.
* El sistema debe detectar duplicados.
* El usuario puede decidir si omite, actualiza o duplica.
* Los enlaces importados deben aparecer en la lista.

**Prioridad:** P1
**Fase:** Fase 2

---

# Épica G — IA futura sin romper la rapidez

---

## HU-031 — Sugerir datos con IA después de guardar

**Como usuario**, quiero que la IA sugiera información después de que el enlace ya esté guardado, para ahorrar tiempo sin esperar.

**Criterios de aceptación:**

* El enlace debe guardarse primero.
* La IA debe ejecutarse después.
* La IA puede sugerir título.
* La IA puede sugerir descripción.
* La IA puede sugerir tipo.
* La IA puede sugerir idioma.
* La IA puede sugerir etiquetas.
* El usuario debe poder aceptar o rechazar sugerencias.

**Prioridad:** P2
**Fase:** Futuro

---

## HU-032 — No sobrescribir datos manuales con IA

**Como usuario**, quiero que la IA no reemplace mis datos sin permiso, para mantener control sobre mi información.

**Criterios de aceptación:**

* Si el usuario escribió un título, la IA no debe cambiarlo automáticamente.
* Si el usuario escribió notas, la IA no debe reemplazarlas.
* Las sugerencias deben mostrarse separadas de los datos reales.
* El usuario debe aceptar los cambios.
* Debe quedar claro qué fue sugerido por IA.

**Prioridad:** P2
**Fase:** Futuro

---

## HU-033 — Procesamiento de IA en segundo plano

**Como usuario**, quiero que la IA trabaje en segundo plano, para que la app siga siendo rápida.

**Criterios de aceptación:**

* La IA no debe bloquear la interfaz.
* La IA no debe bloquear búsquedas.
* La IA no debe bloquear edición.
* Si la IA tarda, la app debe seguir usable.
* Si la IA falla, debe quedar registrado el error sin afectar el enlace.

**Prioridad:** P2
**Fase:** Futuro

---

## HU-034 — Generar resumen automático

**Como usuario**, quiero que la IA genere un resumen del enlace, para recordar rápidamente por qué lo guardé.

**Criterios de aceptación:**

* La IA puede generar un resumen corto.
* El resumen debe ser editable.
* El resumen no debe reemplazar mis notas personales.
* El usuario puede borrar el resumen.
* El resumen debe mostrarse como contenido generado por IA.

**Prioridad:** P2
**Fase:** Futuro

---

# Épica H — Arquitectura técnica Angular + Java

---

## HU-035 — API REST para enlaces

**Como desarrollador**, quiero una API REST en Java, para que Angular pueda guardar, listar, buscar y editar enlaces.

**Criterios de aceptación:**

* Debe existir endpoint para crear enlace rápido.
* Debe existir endpoint para listar enlaces.
* Debe existir endpoint para buscar enlaces.
* Debe existir endpoint para editar enlaces.
* Debe existir endpoint para eliminar o archivar enlaces.
* Las respuestas deben ser JSON.
* Los errores deben ser claros.

**Prioridad:** P0
**Fase:** MVP

---

## HU-036 — Endpoint especial de captura rápida

**Como desarrollador**, quiero un endpoint específico para guardado rápido, para optimizar la acción más importante de la app.

**Endpoint sugerido:**

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
  "status": "PENDING",
  "createdAt": "2026-05-13T10:00:00"
}
```

**Criterios de aceptación:**

* Debe guardar con solo URL.
* Debe responder rápido.
* No debe ejecutar IA.
* No debe esperar metadatos.
* Debe devolver el enlace creado.

**Prioridad:** P0
**Fase:** MVP

---

## HU-037 — Separar frontend y backend

**Como desarrollador**, quiero separar Angular y Java, para que la app sea mantenible y escalable.

**Criterios de aceptación:**

* Angular debe ser una app independiente.
* Java/Spring Boot debe servir la API.
* La URL del backend debe ser configurable.
* Debe funcionar en desarrollo local.
* Debe poder desplegarse después en servidor si se desea.

**Prioridad:** P0
**Fase:** MVP

---

## HU-038 — Base de datos local escalable

**Como desarrollador**, quiero guardar datos en una base local pero preparada para crecer, para empezar simple sin cerrar posibilidades futuras.

**Opciones iniciales:**

```text
SQLite
H2
PostgreSQL local
```

**Recomendación práctica:**

Para escalar mejor después:

```text
PostgreSQL local o SQLite bien estructurado
```

**Criterios de aceptación:**

* Los enlaces deben persistir al reiniciar la app.
* La base debe soportar etiquetas.
* La base debe soportar filtros.
* La base debe soportar migraciones.
* Debe poder moverse a PostgreSQL remoto en el futuro.

**Prioridad:** P0
**Fase:** MVP

---

## HU-039 — Migraciones de base de datos

**Como desarrollador**, quiero usar migraciones, para cambiar el modelo sin perder datos.

**Criterios de aceptación:**

* El backend debe usar Flyway o Liquibase.
* Cada cambio de estructura debe tener migración.
* Las migraciones deben ejecutarse al iniciar.
* El proyecto debe poder recrear la base desde cero.

**Prioridad:** P0
**Fase:** MVP

---

## HU-040 — Carga progresiva en Angular

**Como desarrollador**, quiero que Angular cargue solo lo necesario al inicio, para que la app abra rápido.

**Criterios de aceptación:**

* La pantalla principal debe estar en el bundle inicial.
* Pantallas secundarias deben cargarse con lazy loading.
* Módulos de configuración, estadísticas o IA no deben cargarse al inicio.
* La app debe mostrar contenido útil antes de cargar todo.
* Debe evitar dependencias pesadas innecesarias.

**Prioridad:** P0
**Fase:** MVP

---

# 15. Modelo de datos propuesto

## Tabla `links`

```text
id
url
title
description
notes
type
language
status
priority
favorite
archived
collection_id
save_mode
metadata_status
ai_status
ai_processed
ai_summary
created_at
updated_at
last_opened_at
```

---

## Tabla `tags`

```text
id
name
color
created_at
updated_at
```

---

## Tabla `link_tags`

```text
link_id
tag_id
```

---

## Tabla `collections`

```text
id
name
description
created_at
updated_at
```

---

## Tabla futura `ai_suggestions`

```text
id
link_id
suggested_title
suggested_description
suggested_type
suggested_language
suggested_tags
suggested_summary
status
created_at
accepted_at
rejected_at
```

Esto evita que la IA modifique directamente la información manual.

---

# 16. Endpoints iniciales recomendados

## Enlaces

```text
POST   /api/links/quick
POST   /api/links
GET    /api/links
GET    /api/links/{id}
PUT    /api/links/{id}
PATCH  /api/links/{id}
DELETE /api/links/{id}
```

---

## Acciones rápidas

```text
PATCH /api/links/{id}/favorite
PATCH /api/links/{id}/archive
PATCH /api/links/{id}/status
PATCH /api/links/{id}/tags
```

---

## Búsqueda y filtros

```text
GET /api/links?search=java
GET /api/links?status=PENDING
GET /api/links?favorite=true
GET /api/links?tag=angular
GET /api/links?type=DOCUMENTATION
GET /api/links?language=EN
```

---

## Etiquetas

```text
GET    /api/tags
POST   /api/tags
PUT    /api/tags/{id}
DELETE /api/tags/{id}
```

---

## Exportación/importación

```text
GET  /api/export
POST /api/import
```

---

## IA futura

```text
POST /api/links/{id}/ai/suggest
GET  /api/links/{id}/ai/suggestions
POST /api/links/{id}/ai/accept
POST /api/links/{id}/ai/reject
```

Pero estos endpoints no pertenecen al MVP inicial.

---

# 17. MVP final recomendado

El MVP debe enfocarse en rapidez, no en automatización.

## MVP obligatorio

```text
1. Abrir rápido.
2. Guardar enlace con solo URL.
3. Guardar con Enter.
4. Mostrar confirmación rápida.
5. Crear enlace como pendiente.
6. Ver enlaces recientes.
7. Buscar enlaces.
8. Editar título, descripción y notas.
9. Crear y asignar etiquetas.
10. Marcar favoritos.
11. Filtrar por etiquetas y favoritos.
12. Funcionar localmente.
13. Exportar enlaces.
14. Backend Java con API REST.
15. Frontend Angular con carga liviana.
```

---

## No entra en el primer MVP

```text
IA
Resumen automático
Autocompletado inteligente
Sincronización
Multiusuario
Extensión de navegador
Estadísticas avanzadas
Cifrado avanzado
```

---

# 18. Orden recomendado de desarrollo

## Fase 1 — Base técnica

```text
1. Crear proyecto Angular.
2. Crear proyecto Spring Boot.
3. Configurar base de datos local.
4. Configurar migraciones.
5. Crear entidad Link.
6. Crear API básica de links.
```

---

## Fase 2 — Captura rápida

```text
1. Crear endpoint POST /api/links/quick.
2. Crear campo rápido en Angular.
3. Permitir guardar con Enter.
4. Mostrar confirmación.
5. Mostrar enlaces recientes.
6. Guardar enlaces como pendientes.
```

---

## Fase 3 — Organización básica

```text
1. Crear edición de enlace.
2. Agregar título.
3. Agregar descripción.
4. Agregar notas.
5. Crear etiquetas.
6. Asignar etiquetas.
7. Marcar favoritos.
```

---

## Fase 4 — Búsqueda y filtros

```text
1. Buscar por URL.
2. Buscar por título.
3. Buscar por descripción.
4. Buscar por notas.
5. Filtrar por etiqueta.
6. Filtrar por favorito.
7. Filtrar por pendiente.
```

---

## Fase 5 — Respaldo y experiencia

```text
1. Exportar JSON.
2. Mejorar mensajes.
3. Mejorar pantalla vacía.
4. Agregar modo oscuro.
5. Agregar atajos de teclado.
```

---

## Fase 6 — IA futura

```text
1. Crear estructura de sugerencias IA.
2. Procesar enlaces después de guardarlos.
3. Sugerir título.
4. Sugerir descripción.
5. Sugerir etiquetas.
6. Sugerir tipo.
7. Sugerir idioma.
8. Generar resumen.
```

---

# 19. Requisitos no funcionales de rendimiento

Estos son muy importantes para tu caso.

## RNF-001 — Apertura rápida

```text
La app debe mostrar la pantalla principal en menos de 2 segundos cuando sea posible.
```

---

## RNF-002 — Guardado rápido

```text
Guardar un enlace localmente debe tomar idealmente menos de 500 ms.
```

---

## RNF-003 — No bloqueo por procesos externos

```text
La app no debe esperar servicios externos para guardar enlaces.
```

Esto incluye:

```text
IA
Metadatos
Favicon
Resumen
Clasificación automática
```

---

## RNF-004 — Búsqueda rápida

```text
La búsqueda debe sentirse instantánea para una cantidad normal de enlaces.
```

---

## RNF-005 — Carga progresiva

```text
La app debe cargar primero lo esencial y después lo secundario.
```

Primero:

```text
Campo de guardar enlace
Buscador
Recientes
```

Después:

```text
Filtros avanzados
Configuración
Estadísticas
IA
```

---

## RNF-006 — Funcionamiento offline

Debe funcionar sin internet:

```text
Abrir app
Guardar enlace
Editar enlace
Buscar
Filtrar
Exportar
Ver recientes
```

Puede requerir internet:

```text
Abrir el sitio externo
Obtener metadatos
Usar IA en la nube
Sincronizar
```

---

# 20. Definición de terminado

Una historia está terminada solo si:

* Funciona localmente.
* No hace lenta la captura rápida.
* No obliga a llenar campos opcionales.
* Guarda datos correctamente.
* Tiene mensajes claros.
* Maneja errores sin borrar lo escrito.
* No bloquea la interfaz.
* Persiste al reiniciar.
* Puede probarse manualmente.
* Respeta la regla: **guardar primero, organizar después**.

---

# 21. Resumen final de la idea

La app debe comportarse así:

```text
No me obliga a pensar.
No me obliga a organizar ahora.
No me obliga a esperar.
No me obliga a usar IA.
No me muestra formularios enormes.
No me roba el foco.
```

Y sí debe hacer esto:

```text
Abre rápido.
Guarda rápido.
Busca rápido.
Permite organizar después.
Funciona local.
Está preparada para IA futura.
```

La frase final del proyecto sería:

> **Una app local-first para capturar enlaces al instante, organizarlos después y automatizarlos con IA en el futuro, sin sacrificar velocidad ni foco.**
