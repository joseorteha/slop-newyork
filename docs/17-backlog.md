# 17 — Backlog de ejecución

Estado inicial: documentación preparada; tareas de implementación pendientes. No son issues creados automáticamente.

Cada tarea debe registrar rama, commit/PR, evidencia y resultado. No sustituir la evidencia con una marca de completado.

| ID | Tarea | Depende de | Aceptación |
| --- | --- | --- | --- |
| F0-01 | Verificar JUEGO, contenido, Git y herramientas | — | Raíz correcta, archivos preservados y diagnóstico documentado |
| F0-02 | Capturar línea base del fork | F0-01 | Commit, navegador, equipo y prueba de arranque registrados |
| F0-03 | Preparar entrada independiente TS/Bun | F0-02 | Dev/build/typecheck reproducibles; original conservado |
| F0-04 | Integrar Rapier y sincronización visual | F0-03 | Cuerpo cae, colisiona y se representa en producción |
| F0-05 | Verificar recursos y renderizadores | F0-04 | WASM/modelo cargan bajo subcarpeta; perfiles registrados |
| F1-01 | Definir catálogo y plano v1 ejecutables | F0-04 | IDs, sockets y límites validados con ejemplos |
| F1-02 | Ensamblar grupos rígidos | F1-01 | Masa/centro cambian coherentemente al mover piezas |
| F1-03 | Implementar ruedas y conducción | F1-02 | Dirección/freno/suspensión en pista sin controlador doble |
| F1-04 | Recuperación y ciclo de vida | F1-03 | Reaparece sin solapamiento; sin acumulación tras ciclos |
| F1-05 | Validar diseños de esfuerzo | F1-04 | Casos ligero/pesado/asimétrico y 40 piezas registrados |
| F2-01 | Interacción de colocación por sockets | F1-01, F1-05 | Fantasma válido/inválido y rechazo comprensible |
| F2-02 | Editar con historial | F2-01 | Colocar/quitar/rotar/mover se deshace y rehace correctamente |
| F2-03 | Alternar taller y conducción | F2-02, F1-04 | El borrador se conserva; ensamblaje fallido se revierte |
| F2-04 | Guardar diseños y exportarlos | F2-03 | Round-trip validado y error de almacenamiento recuperable |
| F2-05 | Probar constructor con jugador nuevo | F2-04 | Problemas observados registrados y bloqueantes corregidos |
| F3-01 | Escenario de volúmenes simples | F2-03 | Paso, cuesta y suelo irregular recorribles |
| F3-02 | Sistema de objetivos y recompensas | F3-01 | Eventos duplicados no duplican recompensas |
| F3-03 | Historia breve y desbloqueos | F3-02 | Personaje y cierre conectan los tres desafíos |
| F3-04 | Validar aventura completa | F3-03, F2-05 | Inicio a final sin consola; dos soluciones en un desafío |
| F4-01 | Guía artística y piezas finales | F3-04 | Escala/conectores y licencias comprobados |
| F4-02 | Ambiente, audio y cámaras | F4-01 | Señales legibles y opciones de movimiento/volumen |
| F4-03 | Prueba de atractivo y ajustes | F4-02 | Observaciones externas y cambios documentados |
| F5-01 | Robustecer partida y migraciones | F3-02, F2-04 | Recarga, corrupción e importación cubiertas |
| F5-02 | Compatibilidad y optimización | F4-03 | Matriz y métricas reales, sin promesas no probadas |
| F5-03 | Candidata y revisión de publicación | F5-01, F5-02 | Build versionado, créditos y recorrido final |

## Próxima tarea

F0-01 en una sesión con acceso al directorio local autorizado. Esta documentación puede revisarse en GitHub antes. Para trabajo exclusivamente remoto futuro, definir explícitamente el entorno equivalente antes de crear clones o archivos fuera del límite local del usuario.

## División de cambios

Preferir PRs pequeños que dejen algo verificable: entorno, física, plano, constructor y contenido. Actualizar docs al cambiar contratos. No mezclar reemplazo de toda la ciudad con la primera prueba física.

## Estimaciones

No hay calendario aprobado. Estimar F2–F5 al completar F0/F1, separando programación, arte, diseño y validación. Un objetivo de 15–25 minutos de juego no estima tiempo de producción.
