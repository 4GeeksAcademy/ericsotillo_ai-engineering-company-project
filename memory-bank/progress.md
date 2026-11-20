# Progress: Nexova Solutions

Última actualización: 2026-11-20

## Hecho

- Briefing de la empresa en [BRIEFING.md](../BRIEFING.md) (renombrado desde `CONTEXT.md`).
- Memory bank: [projectbrief.md](projectbrief.md) (negocio) y [techContext.md](techContext.md) (contexto técnico).

## En curso

**Infraestructura para agentes de código (Hito 1)**, rama `feature/agent-memory-bank`: memoria del proyecto, instrucciones, reglas y skills para trabajar con agentes de código en el monorepo.

- Alcance: solo documentación y configuración del agente. En esta iteración no se crean aplicaciones: ni `uis/website`, ni `uis/backoffice`, ni código en `services/`.

## Siguiente

1. Completar la iteración en curso:
   - `AGENTS.md`: archivos de memoria que se leen al iniciar sesión, flujo previo al commit y archivos protegidos.
   - `.gitignore` con secretos y archivos locales.
   - Reglas en `.agents/rules/` y una skill en `.agents/skills/`.
   - Pull request a `main` y merge.
2. Próximas iteraciones previstas, según [README.md](../README.md): Web, Programación, Backend, Telemetría, RAG (Retrieval-Augmented Generation), Agentes, Workflows y Tiempo real. El alcance de cada una se definirá al iniciarla.

## Problemas / bloqueos

| Problema | Impacto | Cuándo se resuelve (previsto) |
| --- | --- | --- |
| `.gitignore` vacío | Un `.env` con secretos se podría versionar | En la iteración en curso |
| `uv sync` falla en `post-create.sh`: no hay `pyproject.toml` | El script de creación del devcontainer se detiene en ese paso | Al crear el primer proyecto Python (backend) |
| `@repo/shared-types`: `main` y `types` apuntan a `index.ts`, pero el archivo está en `types/index.ts` | Importar el paquete fallará | Cuando la primera app use el paquete |

Inconsistencias del briefing pendientes de confirmar: ver [projectbrief.md](projectbrief.md), sección 6.
