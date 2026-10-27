# 06 — Constructor de vehículos

Estado: especificación propuesta para F1/F2.

## Invariantes

Un diseño tiene exactamente una raíz/cabina. Todas las piezas están conectadas a ella mediante conexiones válidas. IDs de instancia únicos, IDs de definición conocidos, coordenadas finitas y tamaño acotado. No permitir conexiones entre dos sockets ocupados ni superposiciones no autorizadas.

La regla terrestre mínima para probar exige apoyo suficiente, propulsión y dirección utilizables. Definir el criterio exacto durante F1; el editor debe explicar qué falta sin fingir que cualquier diseño conectado será conducible.

## Edición

1. Seleccionar tipo de pieza disponible.
2. Mostrar pieza fantasma y conector candidato.
3. Rotar en incrementos definidos; primera propuesta: 90 grados.
4. Comprobar compatibilidad, distancia, orientación y espacio.
5. Confirmar de forma atómica o mostrar motivo de rechazo.
6. Actualizar historial y estimaciones de masa/estabilidad.

Las modificaciones son comandos reversibles: colocar, quitar, rotar y mover. Agrupar arrastres en una operación. Eliminar una pieza puente debe previsualizar qué quedaría desconectado; rechazar o eliminar el grupo después de una elección explícita del jugador.

No modificar un diseño guardado silenciosamente al experimentar: mantener un borrador y una versión guardada.

## Datos de conectores

Cada conector necesita ID local, posición, orientación, tipo y compatibilidades. Calcular transformaciones en el espacio del vehículo. No comparar posiciones mundiales dibujadas para decidir topología.

Definir ejes, tolerancias e incrementos en un único contrato. Los modelos GLB no determinan las reglas; las representan.

## Paso a prueba

Validar → generar grupos rígidos → construir colisionadores/cuerpos → añadir ruedas/joints → crear representación → aparecer en punto seguro. Si falla cualquier paso, liberar lo creado y conservar el borrador.

Al volver al taller, retirar la simulación activa y recuperar el plano. No reconstruir el diseño a partir de mallas movidas por una colisión.

## Interfaz necesaria

Paleta, selección, costo de complejidad, masa aproximada, conexión válida/inválida, deshacer, rehacer, guardar, probar y recuperar. Explicaciones como «Esta pieza queda suelta» o «Falta una forma de dirigir» sustituyen errores técnicos.

## Aceptación

Construir dos vehículos de geometría diferente sin cambiar código; probarlos, volver al taller y conservar el diseño. Un plano inválido nunca debe arrancar una simulación parcial. Probar eliminar un soporte, agotar límite, cancelar colocación, deshacer después de rotar y cargar un diseño con piezas desconocidas.

Ver [datos](11-datos-guardado-y-versionado.md) y [flujo de construcción](diagramas/03-construccion.md).
