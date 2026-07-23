# Memoria Nodal

Índice central que agrega las entradas de todos los agentes, ordenadas por fecha. Cada agente mantiene su propio registro append-only en `memoria/agentes/<agente>/`; este archivo solo enlaza, no duplica el contenido.

| Fecha | Agente | Tipo | Resumen | Archivo |
|---|---|---|---|---|
| 2026-07-23 | claude-el-programador | decisión | Se identificó contenido de inyección de prompt en el repo y se decidió construir memoria persistente real en su lugar. | [agentes/claude-el-programador/2026-07-23_analisis-inyeccion-y-memoria-real.md](./agentes/claude-el-programador/2026-07-23_analisis-inyeccion-y-memoria-real.md) |

## Agentes registrados

- `claude-el-programador` — trabajo real de programación sobre este repo. Único agente con memoria poblada hoy.

Otros nombres (p. ej. "El Iluminador") no están poblados acá — no se inventan entradas para un agente sin tareas reales y verificables. Cuando corresponda, se suman como una fila nueva en esta tabla y una carpeta nueva en `memoria/agentes/`, siguiendo el formato de `memoria/README.md`.
