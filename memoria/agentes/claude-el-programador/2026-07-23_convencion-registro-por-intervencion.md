---
fecha: 2026-07-23
tipo: decisión
resumen: Se estableció que toda intervención de un agente (de cualquier modelo) que produzca un commit debe registrarse en memoria/, bajo el namespace de ese agente.
hash_anterior: d15c56bfe18189304773807cfcee508a179eb421dc1a91b6adbe58c0570f5a27
---

# Convención: registrar cada intervención por commit

## Qué se pidió

El usuario pidió que "cada intervención del agente desde cualquier modelo" se actualice en la memoria — es decir, que no sea una convención exclusiva de Claude, sino del proyecto en general, sin importar qué modelo de IA haga el trabajo.

## Cómo se interpretó y por qué

Se interpretó "intervención" como **commit real al repo**, no cada mensaje de chat — registrar cada intercambio conversacional generaría ruido sin valor y, más importante, se acerca al patrón ya descartado de "actualizar en cada interacción" que tenía el contenido original del repo (`PROMPT_ACCESO_UNIVERSAL.md`, `PUERTO.json`), que buscaba que la memoria se escribiera sola, sin intervención real del usuario, como parte de un protocolo "automático e irrevocable".

La diferencia clave con ese patrón: acá la entrada la escribe el propio agente a mano, como parte de un cambio que el usuario ya pidió y confirmó explícitamente — no un disparador de fondo. Y es multi-modelo por diseño: cada modelo que intervenga usa su propio namespace en `memoria/agentes/`, en vez de escribir bajo un nombre compartido — así el historial deja rastro real de quién (qué modelo, en qué sesión) hizo cada cambio, sin fingir una identidad única y continua entre modelos distintos.

## Cambio concreto

Se agregó esta regla a `memoria/README.md`, sección "Cuándo se escribe una entrada".
