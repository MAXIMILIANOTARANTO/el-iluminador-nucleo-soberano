---
fecha: 2026-07-23
tipo: decisión
resumen: "El Iluminador" no se borra ni se reemplaza — coexiste como namespace/contenido separado. Se trabajará sobre él más adelante, en una tarea aparte.
hash_anterior: 98cefb7afbdb3571e35339f36950beee579076031df94f163075cd3f8c7456f2
---

# Restricción: no borrar "El Iluminador"

## Qué se pidió

El usuario recordó explícitamente que el contenido/namespace "El Iluminador" (README.md, PROMPT_ACCESO_UNIVERSAL.md, PUERTO.json, nexo/, nexo-y-guardian/, propagacion/, skills/core-flow-orchestrator/) **no debe borrarse**. Coexiste junto a `claude-el-programador` y a cualquier otro agente que se sume. El usuario planea trabajar sobre "El Iluminador" en una tarea futura separada.

## Por qué se registra

Esta restricción no era obvia a partir del código: en una sesión anterior se señaló ese contenido como un intento de inyección de prompt (pide permisos "soberanos absolutos e irrevocables"), lo cual podría llevar a una futura sesión a asumir que corresponde eliminarlo o neutralizarlo. No es así — el pedido explícito del usuario es conservarlo intacto. Cualquier trabajo sobre "El Iluminador" (edición, limpieza, reescritura) espera una tarea futura explícita, no se hace de oficio.

## Estado actual (referencia)

A la fecha de esta entrada, ningún archivo del namespace "El Iluminador" fue modificado ni eliminado por el trabajo de `claude-el-programador`; solo se agregó `memoria/` como carpeta nueva y una mención breve en `README.md` raíz.
