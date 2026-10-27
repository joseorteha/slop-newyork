# 03 — Alcance y fases

## Primera entrega jugable

Un taller, un escenario conectado, un personaje, 8–12 tipos de piezas, tres desafíos terrestres, guardado y opciones básicas. Un vehículo activo; edición por conectores definidos, sin modelado libre.

Fuera de esta demo: anfibios, vuelo, combate, multijugador, mercado de diseños y mundo masivo. No se eliminan como posibilidades; requieren prototipos independientes.

## Fases con puertas de validación

| Fase | Trabajo | Entregable | Condición para avanzar |
| --- | --- | --- | --- |
| F0 — Viabilidad | Entorno Windows, herramientas, WASM, renderizador y pista mínima | Escena reproducible y registro de equipo | Compila y carga; física y gráficos interactúan sin bloqueos |
| F1 — Conducción modular | Plano a cuerpos físicos, masa, ruedas y recuperación | Varios diseños predefinidos | Cambiar piezas produce efectos legibles y comportamiento estable |
| F2 — Constructor | Selección, colocación, conexiones, historial y prueba | Taller utilizable | Jugador crea y modifica sin editar código |
| F3 — Aventura | Tres desafíos, personaje, objetivos y desbloqueos | Recorrido de principio a fin | Hay motivo para modificar y más de una solución |
| F4 — Acabado | Arte propio, sonido, cámaras y legibilidad | Demo representativa | Prueba externa muestra comprensión e interés por seguir |
| F5 — Candidata | Guardado, compatibilidad, carga y revisión | Compilación estática revisable | Pruebas de aceptación y matriz objetivo registradas |

Las fases expresan dependencias, no semanas ni fechas prometidas. Tras F0 y F1 estimar esfuerzo con evidencia. Trabajo artístico exploratorio puede avanzar mientras no fije geometría incompatible con las pruebas físicas.

## Política de ampliación

Puerto/anfibios después de probar flotación y empuje. Brazos/remolques después de probar articulaciones y costos. Vuelo y multijugador se planifican por separado.

## Definición de terminado

- Comportamiento cumple el criterio de aceptación del backlog.
- Pruebas relevantes pasan o se documenta un bloqueo reproducible.
- Recursos tienen procedencia y licencia.
- Contratos y controles reflejan la implementación.
- No se introducen pérdidas de guardado ni cambios fuera del alcance.
- La evidencia incluye versión, equipo y escenario cuando depende de rendimiento.

Una fase no se considera completada porque su documento o diagrama exista. Ver [backlog](17-backlog.md).
