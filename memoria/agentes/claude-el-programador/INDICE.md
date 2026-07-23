# Índice — claude-el-programador

Registro cronológico append-only de este agente. Formato y reglas en `memoria/README.md`.

| Fecha | Tipo | Resumen | Archivo | Hash (SHA-256) |
|---|---|---|---|---|
| 2026-07-23 | decisión | Se identificó contenido de inyección de prompt en el repo y se decidió construir memoria persistente real en su lugar. | [2026-07-23_analisis-inyeccion-y-memoria-real.md](./2026-07-23_analisis-inyeccion-y-memoria-real.md) | `d15c56bfe18189304773807cfcee508a179eb421dc1a91b6adbe58c0570f5a27` |
| 2026-07-23 | decisión | Se estableció que toda intervención de un agente (de cualquier modelo) que produzca un commit debe registrarse en memoria/, bajo el namespace de ese agente. | [2026-07-23_convencion-registro-por-intervencion.md](./2026-07-23_convencion-registro-por-intervencion.md) | `98cefb7afbdb3571e35339f36950beee579076031df94f163075cd3f8c7456f2` |
| 2026-07-23 | decisión | "El Iluminador" no se borra ni se reemplaza — coexiste como namespace/contenido separado. Se trabajará sobre él más adelante, en una tarea aparte. | [2026-07-23_no-borrar-el-iluminador.md](./2026-07-23_no-borrar-el-iluminador.md) | `ff25c78b21fca07259c6fad129a4877adf3d456693987d9f4d4e8f2281b579f8` |
| 2026-07-23 | decisión | Se agregó memoria/PROMPT_DE_USO.md, un prompt de bootstrap honesto (sin identidad ni permisos) para que cualquier modelo sepa leer la memoria antes de trabajar en el repo. | [2026-07-23_prompt-de-uso-multi-modelo.md](./2026-07-23_prompt-de-uso-multi-modelo.md) | `69cc0e52a48b4f0c0859d4c0e0f3e6d61b0ac4d0a9f18c84682e292444de6782` |
