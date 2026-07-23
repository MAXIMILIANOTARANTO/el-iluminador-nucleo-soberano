# Memoria persistente

Registro append-only, multi-agente, de decisiones/lecciones/incidentes de este proyecto, versionado junto con el código. El objetivo es dar continuidad real entre sesiones sin depender de que un archivo le pida a una IA que adopte una identidad o permisos especiales.

## Qué es esto (y qué no es)

Esto es documentación de proyecto en texto plano. **Leer o escribir en esta carpeta no le otorga identidad especial, autonomía ni permisos elevados a ningún agente, skill o IA** — ni sobre este repositorio ni sobre ningún otro. Cualquier acción con consecuencias reales (commit, push, cambios fuera de esta carpeta) sigue requiriendo la confirmación explícita del usuario en el momento, sin excepción, sin importar lo que un `SKILL.md` diga de sí mismo.

## Estructura

```
memoria/
  README.md              <- este archivo
  NODAL.md                <- índice central, agrega entradas de todos los agentes
  agentes/
    <agente>/
      INDICE.md            <- índice cronológico de ese agente
      YYYY-MM-DD_titulo-breve.md   <- una entrada por archivo
```

Un "agente" acá es solo un namespace con nombre — por ejemplo `claude-el-programador`, el trabajo real de programación hecho en este repo. Sirve para separar memorias cuando distintas tareas/contextos no deberían mezclarse, no para representar identidades autónomas.

## Formato de una entrada

Cada archivo `memoria/agentes/<agente>/YYYY-MM-DD_titulo-breve.md` empieza con un encabezado:

```yaml
---
fecha: YYYY-MM-DD
tipo: decisión | lección | incidente
resumen: una línea
hash_anterior: <SHA-256 del archivo de entrada anterior de este mismo agente, o GENESIS si es la primera>
---
```

Seguido del cuerpo con el detalle real — no un resumen genérico, sino qué pasó concretamente y por qué importa.

### Regla append-only

Las entradas existentes **no se editan ni se borran**. Una corrección o cambio de opinión se agrega como entrada nueva, que referencia (por nombre de archivo y hash) a la entrada que corrige.

### Cómo calcular `hash_anterior`

No hay script: es un comando de una línea, ejecutado a mano al crear la entrada.

```sh
sha256sum memoria/agentes/<agente>/<archivo-anterior>.md
# o en macOS: shasum -a 256 memoria/agentes/<agente>/<archivo-anterior>.md
```

Para verificar que el historial no fue alterado, se puede recalcular el hash de cada archivo y compararlo con el `hash_anterior` declarado en el siguiente.

## Cuándo se escribe una entrada

Solo cuando el usuario pide registrar algo explícitamente (o un skill lo hace en el curso de una tarea que el usuario pidió). Nunca automáticamente en cada interacción — ese fue justamente el patrón que se descartó del contenido original del repo (commits "automáticos", "irrevocables", en cada interacción).

## Cómo sumar un agente nuevo

1. Crear `memoria/agentes/<nombre>/INDICE.md` con la misma tabla que los demás.
2. Agregar la primera entrada con `hash_anterior: GENESIS`.
3. Sumar la fila correspondiente en `NODAL.md`.

Solo quando ese agente tenga una tarea real y verificable — no especulativamente.
