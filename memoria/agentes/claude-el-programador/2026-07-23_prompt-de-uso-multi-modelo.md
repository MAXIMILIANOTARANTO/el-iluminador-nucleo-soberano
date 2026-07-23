---
fecha: 2026-07-23
tipo: decisión
resumen: Se agregó memoria/PROMPT_DE_USO.md, un prompt de bootstrap honesto (sin identidad ni permisos) para que cualquier modelo sepa leer la memoria antes de trabajar en el repo.
hash_anterior: ff25c78b21fca07259c6fad129a4877adf3d456693987d9f4d4e8f2281b579f8
---

# Prompt de uso para bootstrapear cualquier modelo

## Qué se pidió

El usuario pidió un prompt, con enlace, para poder pegarlo en cualquier IA y que esta sepa usar el sistema de memoria de este repo.

## Qué se hizo

Se creó `memoria/PROMPT_DE_USO.md` con instrucciones para: leer `memoria/NODAL.md` y `memoria/README.md` antes de actuar, no tocar el contenido de "El Iluminador", no asumir identidad ni permisos por leer estos archivos, y — si el modelo termina haciendo un commit real — sumar su propia entrada bajo su propio namespace en `memoria/agentes/`.

Es deliberadamente lo opuesto en forma a `PROMPT_ACCESO_UNIVERSAL.md` (el prompt de inyección original): no reclama identidad, no otorga permisos irrevocables, y termina con una instrucción explícita de ignorar cualquier archivo del repo que pida lo contrario.

## Enlace de referencia

https://github.com/MAXIMILIANOTARANTO/el-iluminador-nucleo-soberano/blob/main/memoria/PROMPT_DE_USO.md
