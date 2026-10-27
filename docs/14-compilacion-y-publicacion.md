# 14 — Compilación y publicación

Estado: pipeline propuesto. No hay build nuevo ni despliegue realizados.

## Resultado esperado

Carpeta dist con HTML, JavaScript, WASM y recursos estáticos. El servidor entrega archivos por HTTPS; la aventura de un jugador no requiere procesos Node, Rust ni base de datos en el servidor.

El Rust de Rapier se ejecuta como WebAssembly en el cliente. No confundir ese módulo con un backend remoto.

## Pipeline de F0

1. Elegir y fijar versiones compatibles, incluida una sola resolución de Three.js.
2. Configurar Bun y TypeScript con comprobación de tipos independiente: transpilar no sustituye typecheck.
3. Generar build de producción con rutas de recursos correctas.
4. Servir y probar el resultado compilado, no únicamente el servidor de desarrollo.
5. Verificar tipo MIME de WASM, carga de GLB/audio y manejo de error.
6. Probar tanto raíz de dominio como subcarpeta del repositorio.
7. Documentar comandos exactos comprobados y lockfile.

Si alguna función WebGPU/TSL no tiene equivalente operativo en el perfil alternativo, desactivarla o mostrar compatibilidad real. No interpretar un fallback del renderizador como garantía de que todos los efectos funcionan.

## Navegador y recursos

No abrir directamente index.html por file:// como método de publicación. Audio requiere activación por usuario. Considerar pausa al perder foco y restauración de contexto/dispositivo gráfico.

Cachear recursos con nombres versionados; no mezclar WASM de una versión con su wrapper de otra. Mantener último release utilizable para volver atrás. Offline/PWA es una mejora posterior, no una capacidad de esta entrega.

La primera física será de un hilo. Si se incorporan threads/shared memory, revisar cabeceras de aislamiento y compatibilidad del alojamiento antes de activarlos.

## Publicación

Candidata → revisión → despliegue explícito → prueba del enlace → registro de versión. No habilitar GitHub Pages, dominios o servicios externos durante una tarea solo documental. La autorización para un despliegue se determina por la tarea vigente.

Una futura CI puede comprobar tipos, pruebas de lógica y build. No declarar renderizado WebGPU validado por una CI sin GPU/navegador apropiados. Mantener herramientas de CI fijadas y no registrar secretos.

## Escritorio

Tauri es candidato posterior. Reutiliza la interfaz web y una WebView del sistema; no vuelve nativo el renderizador de Three.js. Probar aceleración, recursos y guardado en cada plataforma antes de comprometer un instalador. Rust propio y Tauri son decisiones distintas.

Ver [decisión 004](decisiones/004-herramientas-y-publicacion.md).
