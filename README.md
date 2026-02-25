# Software Engineer Skill

Un skill de [Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview) que actua como tu **arquitecto de software personal** — planifica proyectos nuevos desde cero y documenta codebases existentes, cubriendo el ciclo completo desde la idea hasta el scaffold listo para implementar.

## El Problema

Los desarrolladores nos saltamos la planificacion porque se siente lenta. Vamos directo al codigo, y despues pagamos el precio: casos edge no contemplados, cero documentacion, decisiones de arquitectura pobres. Cuando un proyecto ya existe sin documentacion, reconstruirla es igual de doloroso.

## La Solucion

Este skill hace que planificar sea tan rapido y natural como codear. Opera en dos modos:

### Modo Prospectivo (proyecto nuevo)
```
Idea → Preguntas guiadas → Documentacion de ingenieria → Plan de implementacion → Scaffold
```

### Modo Retrospectivo (proyecto existente)
```
Codigo existente → Analisis automatico → Documentacion generada → Gaps identificados → Plan de mejora
```

## Que Genera

Hasta 13 secciones seleccionables de documentacion de ingenieria:

| # | Seccion | Descripcion |
|---|---------|-------------|
| 01 | Arquitectura del Sistema (C4) | Diagramas de contexto y contenedores |
| 02 | Casos de Uso | Flujos detallados con happy path, alternativos y excepciones |
| 03 | Modelo de Dominio | Diagrama de clases conceptual |
| 04 | Diagrama ER | Modelo fisico de base de datos |
| 05 | Catalogo de API | Contratos completos de endpoints |
| 06 | Diagramas de Estado | Ciclo de vida de entidades |
| 07 | Requerimientos | Funcionales y no funcionales |
| 08 | Matriz de Trazabilidad | Cruce requerimientos vs casos de uso |
| 09 | Diagramas de Secuencia | Interaccion entre componentes por caso de uso |
| 10 | Diagramas de Actividad | Flujos de proceso con decisiones |
| 11 | Mapa de Errores | Documentacion de manejo de errores |
| 12 | Matriz de Riesgos | Evaluacion de riesgos tecnicos |
| 13 | Decisiones Tecnicas (ADR) | Registro de decisiones de arquitectura |

Todos los diagramas se generan en formato **Mermaid**.

## Despues de la Documentacion

El skill ofrece un **puente a implementacion**:
- Generar plan de implementacion por fases
- Crear scaffold del proyecto (estructura de directorios + stubs)
- Generar contratos de tests desde la documentacion
- O todo lo anterior

## Instalacion

Copia el directorio `software-architect/` en tu carpeta de skills de Claude Code:

```bash
# Clonar el repo
git clone https://github.com/aburriyo/software-engineer-skill.git

# Copiar al directorio de skills de Claude Code
cp -r software-engineer-skill/software-architect ~/.claude/skills/
```

## Uso

El skill se activa automaticamente cuando dices cosas como:
- "Planifica esta app"
- "Documenta este proyecto"
- "Genera la documentacion de ingenieria"
- "Necesito los docs tecnicos de este codebase"

O invocalo directamente referenciando el nombre del skill.

## Caracteristicas Principales

- **Flujo adaptativo**: Hace preguntas si tu idea es vaga, genera directo si tienes una spec detallada
- **Generacion selectiva**: Elige que secciones generar
- **Auto-deteccion**: Detecta si tienes codigo existente (retrospectivo) o empiezas de cero (prospectivo)
- **Referencias cruzadas**: Los documentos se enlazan entre si (ej: diagramas de secuencia referencian casos de uso)
- **Marcadores de inferencia**: Marca claramente supuestos `[INFERIDO]` y pendientes `[PENDIENTE]`
- **Output configurable**: Por defecto `docs/engineering/`, pero puedes especificar cualquier ruta

## Estructura

```
software-architect/
  SKILL.md                          # Orquestador principal (ligero)
  reference/
    prospective-flow.md             # Flujo de planificacion de proyectos nuevos
    retrospective-flow.md           # Flujo de documentacion de proyectos existentes
    sections-catalog.md             # Templates de las 13 secciones
    implementation-bridge.md        # Generacion de plan + scaffold + tests
```

## Autor

Creado por **Bastian** ([@aburriyo](https://github.com/aburriyo))

## Licencia

Licencia MIT - ver [LICENSE](LICENSE) para mas detalles.
