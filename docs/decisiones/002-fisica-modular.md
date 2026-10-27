# ADR 002 — Rapier y estructura física compuesta

Estado: propuesta principal para F1, pendiente de prueba.

## Contexto

El controlador planar del coche original no cubre vehículos construidos libremente, suspensión y piezas móviles. Un joint por bloque multiplica restricciones y puede generar inestabilidad.

## Decisión

Rapier 3D WASM como autoridad física. Agrupar piezas estructurales en cuerpos compuestos y usar joints solo para mecanismos móviles. Evaluar ruedas por rayos primero.

## Alternativas

Conservar la física planar limita el diseño. Joints rígidos para todo complican estabilidad. Ruedas físicas completas pueden mejorar ciertos contactos, pero aumentan costo y ajuste.

## Consecuencias

La topología del plano determina grupos físicos. Editar exige reconstrucción segura y liberación. Masa e inercia deben derivarse correctamente; flotación y vuelo siguen pendientes.

## Evidencia y revisión

Comparar diseños ligeros, pesados y asimétricos, terreno irregular y límite inicial de piezas. Revisar ruedas si no superan bordillos o contactos necesarios. El motor no sustituye el ajuste jugable.
