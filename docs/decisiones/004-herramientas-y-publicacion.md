# ADR 004 — Bun y distribución web estática

Estado: dirección acordada; compatibilidad por validar.

## Contexto

El usuario prefiere evitar un servidor Node.js. La aventura de un jugador puede ejecutarse en cliente. La base actual usa import map, sin scripts nuevos de Bun.

## Decisión

Probar Bun como herramienta principal y producir archivos estáticos con WASM por HTTPS. No crear backend ni cuentas para la demo. Mantener versión de Three.js fijada hasta validar otra. Tauri y Rust propio diferidos.

## Alternativas

Node como herramienta es técnicamente válido y distinto de un servidor de juego, pero no es la preferencia. Tauri desde el principio añade matriz de WebViews. PWA/offline añade cacheado y actualizaciones antes de una demo.

## Consecuencias

F0 debe comprobar carga WASM, rutas bajo subcarpeta, typecheck y ejecución de pruebas heredadas. No atribuir compatibilidad total a Bun sin probar. Una excepción de herramientas debe registrarse con motivo y alcance.

## Evidencia y revisión

Build servido en Windows/navegador, una sola resolución de Three.js, recursos sin errores y perfiles gráficos operativos. Elegir alojamiento e instalador después de verificar la candidata.
