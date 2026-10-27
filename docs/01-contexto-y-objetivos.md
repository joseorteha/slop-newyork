# 01 — Contexto y objetivos

## Producto acordado

Una aventura de un jugador donde construyes vehículos modulares, pruebas sus capacidades y los modificas para explorar lugares y resolver desafíos. Referencia de mecánica: construcción y experimentación de Trailmakers; la historia, escenarios, modelos e implementación serán propios.

El usuario prioriza impacto visual, un juego bonito y jugable, niveles/progresión y una historia que dé sentido a construir. Se descartaron como dirección principal los repartos, anomalías sobrenaturales y un simple circuito de carreras.

## Restricciones de trabajo

- Repositorio autorizado: joseorteha/slop-newyork, fork del proyecto de mrdoob.
- Carpeta local permitida: `C:\Users\joseo\Documents\PROYECTOS 2026\JUEGO`.
- No modificar otros proyectos ni escribir fuera de esa carpeta. Revisar contenido e instrucciones locales antes de clonar o crear archivos.
- Esta entrega trabaja remotamente dentro de `docs/` del fork. No implica sincronización automática con Windows.
- Conservar Three.js. Se permite sustituir sistemas que no sirvan al nuevo juego, especialmente la física del vehículo.
- Herramientas nuevas: TypeScript, Bun, Rapier/WebAssembly y Blender. Verificar compatibilidad antes de fijar versiones.

## Resultado buscado

El jugador comprende una construcción sin dominar ingeniería, percibe que posición y tipo de piezas importan y tiene una razón para intentar un diseño distinto. La historia y la recompensa abren nuevas posibilidades de construcción.

La primera sesión debe mostrar un resultado visible: montar un vehículo, conducirlo y resolver un obstáculo después de modificarlo. El criterio de impacto es observable en pruebas de jugadores, no el lenguaje elegido.

## Objetivos y exclusiones

| Objetivo | Evidencia |
| --- | --- |
| Construcción accesible | Jugador nuevo arma un diseño válido con ayuda breve |
| Cambios físicos legibles | Explica por qué mejoró o empeoró su diseño |
| Progreso con propósito | Desbloquea y usa una pieza para resolver otro desafío |
| Publicación web viable | Versión de producción funciona en el equipo de referencia |
| Continuidad del proyecto | Contratos, decisiones y pendientes permiten retomarlo |

No hay compromiso inicial de multijugador, móvil, vuelos, destrucción universal, cuentas ni IA generativa durante la partida. La asistencia de IA en desarrollo no impone servicios de IA al juego.

## Argumento provisional

El último taller: recuperar un taller costero y reconectar zonas después de una tormenta. Nombre, personajes, tono y guion pueden evolucionar sin rehacer el constructor. No tratar el argumento como aprobación de cada diálogo o personaje.

Ver [diseño](02-diseno-del-juego.md) y [fases](03-alcance-y-fases.md).
