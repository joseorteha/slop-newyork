# 18 — Fuentes y glosario

## Referencias de implementación

Consultar la documentación correspondiente a las versiones fijadas durante F0. Estos enlaces explican capacidades; no certifican nuestra integración.

| Fuente | Utilidad |
| --- | --- |
| [Base del fork](https://github.com/joseorteha/slop-newyork/commit/1a1cfd85bd3bc4d866afbbb56caf1a3646efc54a) | Estado auditado del código |
| [Three.js WebGPURenderer](https://threejs.org/docs/pages/WebGPURenderer.html) | Backend gráfico y alternativa |
| [Rapier](https://rapier.rs/) | Motor físico Rust y soporte web |
| [Inicio de Rapier JS](https://rapier.rs/docs/user_guides/javascript/getting_started_js/) | Carga de WebAssembly |
| [Articulaciones Rapier](https://rapier.rs/docs/user_guides/javascript/joints/) | Restricciones y cuerpos compuestos |
| [Vehículos Rapier](https://rapier.rs/docs/user_guides/javascript/vehicle_controller/) | Ruedas por rayos y suspensión |
| [Bun bundler](https://bun.com/docs/bundler) | Compilación de recursos web |
| [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) | Persistencia estructurada local |
| [Rust](https://rust-lang.org/) | Propiedades del lenguaje |
| [Tauri y WebViews](https://tauri.app/reference/webview-versions/) | Evaluación futura de escritorio |
| [Mermaid](https://mermaid.js.org/) | Formato de diagramas |
| [Blender](https://www.blender.org/) | Creación de recursos propios |

## Glosario

- **Blueprint/plano:** datos del vehículo que el jugador construyó.
- **Collider/colisionador:** forma simplificada usada para contactos.
- **Cuerpo rígido compuesto:** un cuerpo físico con varias formas de colisión.
- **Socket/conector:** punto y orientación de conexión entre piezas.
- **Joint/articulación:** restricción que permite o limita movimiento relativo.
- **Paso fijo:** intervalo constante de actualización física, separado del dibujo.
- **Interpolación:** representación visual entre poses físicas sucesivas.
- **WebAssembly/WASM:** código compilado que ejecuta el navegador; no es servidor.
- **TSL:** sistema de nodos/materiales de Three.js; no es TypeScript.
- **TypeScript:** lenguaje con comprobación de tipos que se convierte a JavaScript.
- **Bun:** herramienta de ejecución/paquetes/compilación; no motor gráfico.
- **Vertical slice/demo representativa:** tramo breve con construcción, desafío, historia y acabado.
- **ADR:** registro de una decisión de arquitectura y sus consecuencias.
- **Upstream:** repositorio original del que deriva el fork.
- **Idempotente:** repetir un evento no duplica su efecto.
