# 04 — Análisis del repositorio original

## Base y método

Fork inspeccionado: joseorteha/slop-newyork, commit `1a1cfd85bd3bc4d866afbbb56caf1a3646efc54a`. Incluye cambios posteriores al análisis preliminar sobre `a3c478a`. Inventario remoto: 86 entradas; sin docs ni AGENTS.md en el árbol de esa base.

La revisión es de código y estructura, no una certificación gráfica. El anuncio de 60 FPS del HTML no demuestra rendimiento en el equipo del usuario. Las pruebas realizadas previamente sobre otra revisión no validan automáticamente este fork.

## Arquitectura actual observada

| Archivo o grupo | Responsabilidad | Implicación |
| --- | --- | --- |
| [index.html](../index.html) | Import map, interfaz y módulos nativos | No hay pipeline Bun/TypeScript configurado |
| [main.js](../js/main.js) | Arranque, mundo, controladores, audio y bucle | Separar composición de aplicación y dominio |
| [controllers.js](../js/controllers.js) | Persona, coche, bici y helicóptero | No implementa posesión arbitraria de vehículos |
| [vehicle-physics.js](../js/vehicle-physics.js) | Contactos planares e impulsos de vehículos | No es la simulación modular 3D propuesta |
| [traffic.js](../js/traffic.js) | Carriles, circulación y choques | Tráfico ambiental, no sistema general de misiones |
| [road-network.js](../js/road-network.js) | Red vial dirigida e intersecciones | Útil para ciudad vial, innecesaria para la primera pista |
| [buildings.js](../js/buildings.js) y [city-grid.js](../js/city-grid.js) | Construcción de Manhattan | Fuertemente ligados a geografía y configuración |
| [cameras.js](../js/cameras.js) | Seguimiento, cabina y vistas | Adaptar detrás de un objetivo de cámara genérico |
| [scene-culling.js](../js/scene-culling.js) | Fragmentación espacial y descarte | Reutilizar conceptos, revisar dependencia de escena |
| [tsl-materials.js](../js/tsl-materials.js) | Materiales procedurales | Extraer únicamente los necesarios |
| [audio-system.js](../js/audio-system.js) | Sonido de ciudad y eventos | Acoplado a controladores/tráfico; necesita adaptador |

Three.js está fijado en el HTML al commit `f17eb5d689094a3fbd4cd0d64d54729a48036ce0`. No reemplazarlo por una versión distinta sin probar materiales, addons y sombras conjuntamente.

## Límites relevantes

- La altura de coche y bici se ajusta a superficies específicas en el controlador, sin un sistema general de suspensión y saltos.
- Los interiores aparentes de ventanas son shaders, no habitaciones transitables.
- El mapa dibuja una ruta simplificada, no una búsqueda vial completa.
- Coches y peatones lejanos se reciclan. Un actor de misión requeriría persistencia propia.
- La aplicación congela actualizaciones automáticas de matrices del mundo y mantiene raíces dinámicas explícitas.
- Los listeners de colisiones existentes son individuales; para múltiples consumidores haría falta distribución de eventos.
- No hay constructor modular, capítulos ni guardado de planos.

## Estrategia de adaptación

Conservar el fork y su historial. Construir una entrada de prototipo separada en una fase posterior, sin eliminar el original. Extraer cámaras, iluminación y controles a través de adaptadores pequeños. Integrar Rapier como autoridad de la nueva simulación; no ejecutar dos físicas sobre el mismo vehículo.

El escenario inicial propio no necesita cargar Manhattan ni sus geodatos. No copiar todo el sistema de tráfico por inercia. Mantener pruebas originales mientras los componentes correspondientes sigan en uso.

## Auditoría pendiente

Medir costo real del renderizador y compilación de shaders, validar modo WebGL2, revisar compatibilidad Bun de pruebas heredadas y comprobar licencias al extraer recursos. Los resultados pertenecen al [registro de pruebas](12-pruebas-y-rendimiento.md).
