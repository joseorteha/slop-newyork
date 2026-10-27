# 08 — Mundo, historia y misiones

Estado: contenido propuesto. La aventura completa todavía no existe.

## Mundo inicial

Taller y patio de pruebas conectados con un barrio costero, una cuesta y un camino irregular. Geometría diseñada para probar anchura, tracción y estabilidad. Mantener distancias cortas entre ensayo y desafío; evitar minutos de desplazamiento repetitivo.

Construir primero con volúmenes simples y colisionadores visibles en depuración. Validar las dimensiones contra vehículos antes de hacer arte final. El escenario debe tener espacios de recuperación y una ruta de regreso.

## Historia propuesta

El protagonista recupera un taller y ayuda a reconectar lugares después de una tormenta. Un personaje presenta el primer problema y reconoce los avances. Tono cálido y curioso, con humor en las construcciones.

El nombre, parentesco con el antiguo dueño y diálogos finales siguen abiertos. No producir cinemáticas extensas antes de probar el juego.

## Modelo de misión

Cada misión declara ID estable, requisitos, objetivos, eventos admitidos y recompensa. Estados: bloqueada, disponible, activa y completada. El progreso se guarda; recompensas se conceden una sola vez.

Triggers del mundo emiten eventos de dominio: entrar en zona, alcanzar meta, activar interacción. No completar misiones por nombre de malla ni por mostrar un diálogo. Validar que el vehículo cumple la condición al cruzar una meta para evitar éxitos accidentales.

## Secuencia de demo

| ID propuesto | Objetivo | Resultado |
| --- | --- | --- |
| tutorial.taller | Crear y probar primer vehículo | Abrir salida del taller |
| barrio.paso | Alcanzar meta a través del sector estrecho | Presentar alternativas de geometría |
| cerro.subida | Llegar a la plataforma superior | Desbloquear mejora de tracción |
| camino.regreso | Superar el camino irregular | Cierre y acceso a ensayo libre |

Son identificadores de diseño, no misiones cargables todavía. Las recompensas exactas deben permitir progresar y no obligar a un único plano.

## Guardado y repetición

Completar misión y otorgar recompensa en una transacción lógica. Reprocesar el mismo evento no duplica piezas. Reiniciar desafío conserva desbloqueos. Cargar partida reconstruye el estado visual desde progreso, sin repetir recompensas.

## Expansión

Puerto/anfibio, zona industrial/mecanismos e isla/faro son candidatos posteriores. Cada región debe añadir un problema mecánico distinto y permitir reutilizar diseños anteriores.

Ver [progreso y guardado](diagramas/05-progreso-y-guardado.md) y [persistencia](11-datos-guardado-y-versionado.md).
