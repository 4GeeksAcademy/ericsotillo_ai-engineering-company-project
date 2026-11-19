# Project brief: Nexova Solutions

Fuente de verdad: [BRIEFING.md](../BRIEFING.md).

## 1. Empresa

Consultora de recursos humanos y selección de talento fundada en 2011. Sede en Valencia (España) y oficina en Miami. 120 empleados, unos 8 millones de dólares anuales. Líneas: headhunting de mandos medios y directivos, outsourcing de equipos de soporte al cliente y formación en habilidades blandas y liderazgo. Clientes: medianas empresas de tecnología, retail y servicios financieros que externalizan su gestión del talento.

## 2. Problema

Nexova no puede operar a escala: trabajo manual y herramientas desconectadas, sin telemetría ni registros centralizados. Consecuencias: consultores en tareas automatizables, clientes sin visibilidad de sus procesos, catálogo de formación invisible, soporte que incumple su Service Level Agreement (SLA) y dirección con datos de hace una semana. Urgencia: plataformas automatizadas ya compiten directamente y la ventana es limitada.

## 3. Áreas y necesidades

Detalle en [BRIEFING.md](../BRIEFING.md#the-departments-and-their-problems).

| Área                       | Responsable                                           | Necesidad principal                                               |
| -------------------------- | ----------------------------------------------------- | ----------------------------------------------------------------- |
| Selección                  | Javier Almeida                                        | Scoring y ranking automático de currículum vítae (CV)             |
| Formación                  | Elena Vargas                                          | Catálogo con inscripción online y recomendación de programas      |
| Soporte externalizado      | Roberto Díaz                                          | Chatbot que resuelva el 40 % de consultas sin intervención humana |
| Ventas                     | Megan Clarke o Marcos Ibáñez (pendiente de confirmar) | Prospección automatizada y alertas de seguimiento                 |
| Marketing                  | Carmen Ruiz                                           | Web rediseñada y medición de conversión                           |
| Recursos Humanos (interno) | Patricia Solís                                        | Portal interno con onboarding automatizado                        |
| Tecnología                 | Sergio Molina                                         | Telemetría, logging centralizado y pipeline de datos              |
| Dirección Ejecutiva        | Laura Mendoza                                         | Dashboard unificado en tiempo real                                |

## 4. Objetivos del proyecto

Sistemas, automatizaciones y herramientas inteligentes para que Nexova haga lo que ya hace bien más rápido, a mayor escala y con menos esfuerzo manual.

- **Por área**: dashboards sobre un pipeline de datos común, portales (candidatos, alumnos, empleados), automatizaciones con alertas y análisis de sentimiento de tickets.
- **Capacidades de inteligencia artificial (IA)**: scoring y ranking de CV; Retrieval-Augmented Generation (RAG) sobre la base de candidatos y en el chatbot de soporte; búsqueda semántica en la base de conocimiento de soporte; recomendación de programas formativos; contenido asistido por IA; agentes para emails a candidatos, propuestas comerciales, consultas de Recursos Humanos, planes formativos, arquitectura técnica y consultas de dirección en lenguaje natural.

## 5. Restricciones de negocio

- **SLA de soporte**: 24 h comprometidas; hoy 48 h de media (BRIEFING.md › Customer Support (outsourced service)).
- **Datos personales** de candidatos y empleados: nunca reales en repositorio, logs ni prompts; en desarrollo, ficticios. _Inferencia_: opera en la Unión Europea (BRIEFING.md › introducción) y trata datos de personas.
- **Decisiones sobre personas**: la IA propone (scoring, rankings, respuestas); una persona decide o recibe lo que la IA no resuelve. _Inferencia_: chatbot que resuelve solo el 40 % sin intervención humana (BRIEFING.md › Customer Support (outsourced service)).

## 6. Inconsistencias y ambigüedades conocidas

- **Responsable de Ventas**: Megan Clarke (BRIEFING.md › How the company is organised) vs Marcos Ibáñez (BRIEFING.md › Sales and Business Development). Pendiente de confirmar.
- **Formación**: recomendación por perfil de empresa cliente (BRIEFING.md › Corporate Training, explícito); ¿"planes personalizados" del chatbot por empresa o por alumno? Pendiente de confirmar.
