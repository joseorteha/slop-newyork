# Diagrama 06 — Desarrollo y distribución

Estado: pipeline propuesto, sin despliegue realizado.

```mermaid
flowchart LR
    SRC["TypeScript y recursos"] --> BUILD["Bun build y typecheck"]
    GLB["Blender y exportados GLB"] --> BUILD
    WASM["Rapier WASM fijado"] --> BUILD
    BUILD --> DIST["Archivos de produccion"]
    DIST --> REVIEW["Pruebas y candidata revisable"]
    REVIEW --> HOST["Alojamiento estatico HTTPS"]
    HOST --> WEB["Navegador en computadora"]
    WEB --> GPU["WebGPU o perfil WebGL2 probado"]
    WEB --> SAVE["IndexedDB local"]
    SAVE --> FILE["Respaldo exportable"]
    DIST -.-> DESK["Evaluacion futura de Tauri"]
```

No hay servidor de juego para la demo de un jugador. Bun prepara archivos; no necesita ejecutarse en la computadora del jugador. Tauri no está aprobado como sustituto nativo del renderizador.

Ver [publicación](../14-compilacion-y-publicacion.md).
