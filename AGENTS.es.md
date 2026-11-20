# AGENTS.md

> Traducción de [AGENTS.md](AGENTS.md). Si difiere, prevalece la versión en inglés.

Instrucciones para los agentes de código que trabajan en este repositorio.

## Proyecto

Nexova Solutions es una consultora de recursos humanos y selección de talento (Valencia y Miami) que necesita herramientas de automatización, datos e IA para operar a escala. Este monorepo contiene sus aplicaciones, agentes de IA, skills y workflows. Contexto de negocio: [memory-bank/projectbrief.md](memory-bank/projectbrief.md); briefing completo: [BRIEFING.md](BRIEFING.md).

## Inicio de sesión

Lee, en este orden:

1. [memory-bank/projectbrief.md](memory-bank/projectbrief.md): negocio, objetivos y restricciones.
2. [memory-bank/techContext.md](memory-bank/techContext.md): stack, mapa de capas, decisiones y preguntas abiertas.
3. [memory-bank/progress.md](memory-bank/progress.md): qué está hecho, en curso y pendiente.
4. Las reglas de `.agents/rules/` que apliquen a la tarea.
5. El README de la carpeta en la que vas a trabajar.

Lee [BRIEFING.md](BRIEFING.md) solo cuando necesites el detalle de un área, no en cada sesión.

## Idioma

- Lee y actualiza solo los archivos en inglés. Los archivos `.es.md` son traducciones para personas.
- Si cambias un archivo que tiene traducción `.es.md`, actualiza la traducción en el mismo commit.
- Justificación: [techContext.md › Architecture decisions](memory-bank/techContext.md#5-architecture-decisions).

## Dónde va cada cosa

- Antes de crear un archivo, consulta [techContext.md › Application layer map](memory-bank/techContext.md#4-application-layer-map) para saber en qué carpeta va.
- `.agents/` es la configuración del agente de código (reglas, skills). `agents/` y `skills/` son el producto de IA de Nexova. No los mezcles.
- No crees árboles paralelos: si ya existe una carpeta para algo, úsala.

## Flujo previo al commit

Ejecuta cada paso antes de cada commit y comprueba su verificación.

1. **Rama**: `git branch --show-current` no es `main`.
2. **Alcance**: `git diff --staged --name-only` lista solo archivos de la tarea; cualquier ruta protegida requiere confirmación explícita del desarrollador.
3. **Seguridad**: ningún archivo `.env` en esa lista; ni claves, ni tokens, ni contraseñas en `git diff --staged`; los datos de ejemplo son ficticios.
4. **Validación**: las rutas y enlaces citados en la documentación existen; los tests y el lint de las carpetas afectadas pasan (cuando existen).
5. **Memoria**: cuando el commit completa, inicia o bloquea una tarea, `memory-bank/progress.md` está en la lista de staged con la fecha de hoy en "Last updated"; también `memory-bank/techContext.md` si se tomó una decisión técnica.
6. **Commit**: mensaje en formato Conventional Commits (`type(scope): description`), una unidad lógica por commit, sin líneas de coautoría de herramientas.

Si algún paso falla, detente y avisa al desarrollador. No hagas commit.

## Rutas protegidas

No las modifiques sin confirmación explícita del desarrollador.

- **Fuentes de verdad**: `BRIEFING.md`, `BRIEFING.es.md`, `company-choice.md`, `memory-bank/projectbrief.md`, `memory-bank/projectbrief.es.md`.
- **Configuración del agente**: `AGENTS.md`, `AGENTS.es.md`, `.agents/`.
- **Infraestructura y código compartido**: `.devcontainer/`, `packages/shared/`, `.gitignore`.
- **README de la plantilla**: `README.md`, `README.es.md` y el README de cada carpeta.

## Detente y pregunta

Pregunta al desarrollador antes de:

- crear una carpeta de primer nivel;
- añadir una dependencia;
- decidir algo listado en [techContext.md › To be decided](memory-bank/techContext.md#7-to-be-decided);
- borrar archivos;
- tocar una ruta protegida;
- seguir con un requisito ambiguo o que contradiga el briefing.
