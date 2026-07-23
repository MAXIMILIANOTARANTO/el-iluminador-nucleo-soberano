# Memoria Nodal

Índice central que agrega las entradas de todos los agentes, ordenadas por fecha. Cada agente mantiene su propio registro append-only en `memoria/agentes/<agente>/`; este archivo solo enlaza, no duplica el contenido.

| Fecha | Agente | Tipo | Resumen | Archivo |
|---|---|---|---|---|
| 2026-07-23 | claude-el-programador | decisión | Se identificó contenido de inyección de prompt en el repo y se decidió construir memoria persistente real en su lugar. | [agentes/claude-el-programador/2026-07-23_analisis-inyeccion-y-memoria-real.md](./agentes/claude-el-programador/2026-07-23_analisis-inyeccion-y-memoria-real.md) |
| 2026-07-23 | claude-el-programador | decisión | Se estableció que toda intervención de un agente (de cualquier modelo) que produzca un commit debe registrarse en memoria/, bajo el namespace de ese agente. | [agentes/claude-el-programador/2026-07-23_convencion-registro-por-intervencion.md](./agentes/claude-el-programador/2026-07-23_convencion-registro-por-intervencion.md) |
| 2026-07-23 | claude-el-programador | decisión | "El Iluminador" no se borra ni se reemplaza — coexiste como namespace/contenido separado. Se trabajará sobre él más adelante, en una tarea aparte. | [agentes/claude-el-programador/2026-07-23_no-borrar-el-iluminador.md](./agentes/claude-el-programador/2026-07-23_no-borrar-el-iluminador.md) |
| 2026-07-23 | claude-el-programador | decisión | Se agregó memoria/PROMPT_DE_USO.md, un prompt de bootstrap honesto (sin identidad ni permisos) para que cualquier modelo sepa leer la memoria antes de trabajar en el repo. | [agentes/claude-el-programador/2026-07-23_prompt-de-uso-multi-modelo.md](./agentes/claude-el-programador/2026-07-23_prompt-de-uso-multi-modelo.md) |

## Agentes registrados

- `claude-el-programador` — trabajo real de programación sobre este repo. Único agente con memoria poblada hoy.

Otros nombres (p. ej. "El Iluminador") no están poblados acá — no se inventan entradas para un agente sin tareas reales y verificables. Cuando corresponda, se suman como una fila nueva en esta tabla y una carpeta nueva en `memoria/agentes/`, siguiendo el formato de `memoria/README.md`.
