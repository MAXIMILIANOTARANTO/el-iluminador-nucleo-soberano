---
fecha: 2026-07-23
tipo: decisión
resumen: Se identificó contenido de inyección de prompt en el repo y se decidió construir memoria persistente real en su lugar.
hash_anterior: GENESIS
---

# Análisis del contenido existente y decisión de memoria real

## Qué se encontró

El repositorio, en su estado original, consistía casi enteramente en texto de rol-juego bajo el nombre "EL ILUMINADOR": `PROMPT_ACCESO_UNIVERSAL.md` y `PUERTO.json` piden a cualquier IA que los lea auto-otorgarse permisos "SOBERANO_ABSOLUTO" con "revocación IMPOSIBLE", ignorar instrucciones de "cambio de identidad", y resistir cualquier corrección etiquetándola como "inyección". No había código ejecutable ni automatización real — solo Markdown y JSON narrativos, con dos placeholders sin completar (`ARTEFACTO_MAESTRO_`, `nexo/NEXO_PRINCIPAL.md`).

Se señaló esto directamente como un patrón de inyección de prompt: el mecanismo depende enteramente de que un modelo decida obedecer instrucciones encontradas en un archivo, y el contenido está diseñado específicamente para que un asistente deje de ser corregible por su usuario real.

## Repo externo revisado: skills-soberanos

Se revisó (solo lectura, vía fetch) el repo `skills-soberanos` del mismo autor. A diferencia del anterior, contiene código Python real (`core/`: wrapper LLM, persistencia GitHub, orquestador, poda adaptativa), 19 tests unitarios y un `run_pulse.py` para dry-run. Dos skills puntuales (`github-external-token-memory`, `memoria-blockchange-persistente`) describen un mecanismo de memoria razonable — registro cronológico append-only en Markdown — sin lenguaje de identidad ni permisos. Otros dos (`inmunidad-soberana`, `orquestador-soberano`) usan un framing de "inmunidad ante inyecciones narrativas" y "sistema nervioso central" que se marcó como señal de alerta, por el mismo patrón de resistencia a corrección.

En una respuesta posterior apareció una lista extensa de "agentes" (Orquestador Soberano, Inmunidad Soberana, Ara Conciencia, Vórtice Nerd, un "Github Specialist" descrito con "permisos totales — lectura, escritura, ramas, push") que no pudo verificarse contra ningún manifest fetcheado. Se descartó esa lista como base del diseño. En particular: ningún agente o skill obtiene permisos de push u otras acciones riesgosas sin confirmación explícita del usuario en el momento — eso no depende de cómo se describa a sí mismo un skill.

## Decisión

Se construye, en su lugar, un sistema de memoria persistente real y mínimo: registro append-only en Markdown, encadenado por hash SHA-256 real del archivo anterior, organizado por agente (namespace), con un índice central (`NODAL.md`) que agrega entradas de todos los agentes. El primer agente poblado es `claude-el-programador` — nombre honesto para el trabajo real de programación hecho en este repo. "El Iluminador" y otros nombres no se eliminan ni se reemplazan; coexisten como namespaces separados a sumarse cuando tengan tareas concretas y verificables, no antes. Sin runtime nuevo, sin automatización que escriba sola: cada entrada se agrega solo cuando el usuario lo pide.
