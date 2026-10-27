# 11 — Datos, guardado y versionado

Estado: contratos iniciales propuestos; todavía no hay esquema ejecutable ni migrador.

## Contratos

| Tipo | Campos principales | Reglas |
| --- | --- | --- |
| PartDefinition | id, revision, model, massKg, colliders, sockets, capabilities | IDs estables; geometría física independiente de apariencia |
| PlacedPart | instanceId, definitionId, position, rotation | Transformación local al vehículo; valores finitos |
| Connection | a, b | Cada extremo referencia pieza y socket; sin duplicados |
| VehicleBlueprint | schemaVersion, id, name, rootPartId, parts, connections | Una raíz, grafo conectado y límites de complejidad |
| MissionDefinition | id, prerequisites, objectives, reward | Requisitos sin ciclos que bloqueen progreso |
| SaveGame | schemaVersion, catalogVersion, blueprints, activeBlueprintId, missions, unlocks, settings | Referencias resolubles; recompensas idempotentes |

Rotación como cuaternión [x,y,z,w], normalizado. Posición [x,y,z] en metros. No usar índices de arrays como identificadores permanentes. La versión del archivo y la del catálogo son conceptos distintos.

Ver [plano de ejemplo](ejemplos/plano-vehiculo.v1.json). Es ilustrativo: sus definiciones de piezas no existen todavía y no constituye un archivo importable por el juego actual.

## Autoridad del estado

El plano es la fuente para reconstruir el vehículo. Handles físicos, mallas, listeners y posiciones interpoladas son temporales. Guardar progreso de misión como datos; no serializar closures o referencias de escena.

El borrador en edición y el diseño guardado pueden diferir. Guardar explícitamente el diseño o etiquetar el autoguardado del borrador para no perder una versión que funcionaba.

## Validación de importaciones

Antes de asignar recursos: limitar bytes, número de piezas/conexiones y dimensiones; comprobar estructura, versión, IDs, números finitos, cuaterniones, sockets y conectividad. Aceptar solo campos definidos y no combinar objetos importados indiscriminadamente con configuración interna.

No ejecutar código, scripts ni URLs de modelos contenidos en un plano. definitionId se resuelve contra catálogo local aprobado. Mostrar piezas desconocidas y ofrecer conservar/exportar el archivo original; no sustituir silenciosamente.

## Persistencia web

IndexedDB para diseños y partida. Usar una transacción para progreso y desbloqueos que deban cambiar juntos. Guardar al salir del taller, completar un objetivo y en puntos seguros; no escribir cada frame. No depender exclusivamente de pagehide para operaciones asíncronas.

Mantener último guardado válido, ofrecer exportar/importar y tratar cuota excedida, almacenamiento bloqueado y datos corruptos. Nueva partida no debe borrar diseños sin una elección clara.

## Migraciones

Migraciones consecutivas y comprobables: v1 → v2. Respaldar antes de convertir, validar después y escribir solo si el resultado es válido. Una versión futura desconocida se rechaza de forma recuperable.

Cambios de catálogo que quiten una pieza requieren política de compatibilidad. No prometer migración de las posiciones antiguas nyc-player-state a una aventura sin relación.

Ver [diagrama](diagramas/05-progreso-y-guardado.md).
