# ADR 003 — Planos versionados y persistencia local

Estado: dirección acordada; esquema inicial propuesto.

## Contexto

El jugador debe conservar y compartir diseños sin depender de objetos de una sesión física o gráfica. El juego inicial no requiere cuentas.

## Decisión

Guardar VehicleBlueprint y SaveGame como datos versionados con IDs estables. IndexedDB para partida y diseños, más exportación/importación validada. Fuente de reconstrucción: plano, no mallas.

## Alternativas

Serializar escena completa acopla versiones y recursos. Guardar solo en memoria pierde progreso. Backend de cuentas añade operación y red antes de demostrar su utilidad.

## Consecuencias

Necesitamos validación, migraciones y política para piezas desconocidas. El almacenamiento del navegador puede borrarse o fallar; el respaldo descargable es parte del flujo. Progreso y recompensas relacionados deben persistir juntos.

## Evidencia y revisión

Round-trip, recarga, importación malformada y migración. Revisar servicio remoto solo si compartir/sincronizar se vuelve un requisito aprobado.
