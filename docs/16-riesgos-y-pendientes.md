# 16 — Riesgos y pendientes

## Riesgos de ejecución

| Riesgo | Señal temprana | Respuesta y fase |
| --- | --- | --- |
| Construcciones inestables | Vibración, penetración o impulsos explosivos | Cuerpos compuestos y pruebas F1 |
| Manejo poco divertido | Jugadores no relacionan controles y respuesta | Ajustar suspensión y cámara antes de F3 |
| Constructor confuso | Necesidad continua de ayuda | Simplificar conexiones y probar F2 |
| Acoplamiento a Manhattan | Cada extracción arrastra geodatos/tráfico | Adaptadores y entrada mínima en F0 |
| Compatibilidad Bun/WASM | Build funciona solo en desarrollo | Prueba de producción F0 |
| Cambio de Three.js incompatible | Shaders/addons fallan al actualizar | Fijar conjunto compatible y comparar |
| Alto costo gráfico | p95 se dispara con sombras/reflejos | Perfil reducido y mediciones F0/F4 |
| Pérdida de diseños | Guardado inválido o catálogo incompatible | Versiones, respaldo y transacciones F2/F5 |
| Alcance excesivo | Agua/vuelo antes de constructor estable | Respetar puertas de fases |
| Licencias incompletas | Recurso sin fuente o permiso | Inventario antes de incorporarlo |
| Carpeta local inaccesible | Sesión remota sin disco de Windows | No simular acceso; usar GitHub y sincronizar después |

## Preguntas abiertas que no bloquean documentar

- Nombre definitivo, personaje y guion.
- Equipo mínimo y matriz de compatibilidad.
- Dimensiones de conectores y presupuesto definitivo de piezas.
- Propulsión como módulo independiente o capacidad integrada.
- Comportamiento de batería: decorativo, capacidad o consumo.
- Versión exacta de Three.js/Rapier/Bun comprobada.
- Editor inicial separado o acceso integrado dentro del menú.

## Decisiones que sí bloquean fases

Antes de F1: confirmar carga WASM/build y autoridad física única.
Antes de F2: contrato de piezas, sockets y plano.
Antes de F3: conducción estable y edición comprensible.
Antes de publicación: guardado, licencias y resultados de compatibilidad.

## Cambios de dirección

Un cambio de motor, multijugador o simulación completa de piezas rompe supuestos del plan. Registrar motivación, alternativas, costo y efectos en una decisión nueva antes de extender la implementación.

No inventar porcentajes de avance ni fechas para cerrar incertidumbres. Cada riesgo se reduce con una prueba identificable, cuyo resultado se registra en [pruebas](12-pruebas-y-rendimiento.md).
