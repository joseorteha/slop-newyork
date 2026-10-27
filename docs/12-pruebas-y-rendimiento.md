# 12 — Pruebas y rendimiento

## Estado de evidencia

Esta entrega es documental. No se han ejecutado en esta rama pruebas del futuro juego, benchmarks de GPU ni partidas en Windows. Validar documentos y enlaces no demuestra que la integración Rapier/Bun exista.

El fork contiene pruebas heredadas en tests; no atribuirles cobertura del constructor o de los contratos propuestos. Hay pruebas con dependencias Node y scripts Bash. La compatibilidad con Bun/Windows se evalúa en F0, no se asume.

## Matriz de aceptación

| Área | Casos | Evidencia requerida |
| --- | --- | --- |
| Plano | Duplicados, raíz ausente, desconexión, piezas desconocidas y límites | Pruebas unitarias de validación |
| Editor | Colocar, cancelar, mover, borrar puente, deshacer/rehacer | Pruebas de comandos y revisión interactiva |
| Física | Plano ligero/pesado/asimétrico, cuesta, vuelco y frenado | Recorridos repetibles y parámetros registrados |
| Tiempo | 30/60/120 FPS de representación; pausa y pestaña suspendida | Comportamiento comparable con paso fijo |
| Ciclo de vida | 50 cambios taller/prueba y recuperaciones repetidas | Sin cuerpos/listeners acumulados ni crecimiento sostenido |
| Persistencia | Recarga, exportación, importación, corrupción y migración | Round-trip y fallos recuperables |
| Misiones | Evento duplicado, cargar tras recompensa, repetir desafío | Progreso y recompensas idempotentes |
| Producción | Rutas bajo subcarpeta, WASM, modelos y audio | Recorrido completo servido por HTTPS |

No escribir pruebas de detalles visuales triviales. Priorizar invariantes, fallos que pierdan datos y comportamiento físico.

## Equipos y navegadores

Definir en F0 equipo mínimo de referencia y principal: CPU, GPU, RAM, sistema, resolución, escala y navegador/versiones. Primera matriz propuesta: Windows con Chromium (Chrome/Edge) y Firefox, tanto WebGPU como alternativa donde proceda. Safari y otros sistemas quedan sin certificación hasta probarlos.

Probar control por teclado/ratón; mando como objetivo adicional. No prometer compatibilidad móvil.

## Objetivos provisionales

- 60 FPS en equipo de referencia a 1080p/calidad acordada; 16.7 ms por frame es presupuesto global, no por sistema.
- Un vehículo activo y 40 piezas como caso inicial de esfuerzo.
- Medir p50/p95 de frame, física y carga; registrar calentamiento de shaders.
- Medir bytes transferidos, tiempo hasta interacción y memoria tras ciclos repetidos.
- Fijar umbrales de carga y memoria después de la línea base, no inventar cifras sin equipo.

Medir CPU y GPU por separado cuando las herramientas lo permitan. No sumar tiempos superpuestos como si fueran secuenciales. Evitar que observabilidad modifique significativamente el resultado.

## Pruebas de jugadores

Al menos una sesión breve con personas que no conozcan el proyecto. Observar si construyen, entienden el fallo y desean volver a probar. Registrar ayuda, intentos y confusiones; no convertir una muestra pequeña en una afirmación de mercado.

## Plantilla de resultado

```text
ID de prueba:
Commit / build:
Fecha y entorno:
Equipo, navegador, resolución y perfil:
Escenario y plano:
Pasos:
Esperado / observado:
Métricas y evidencia:
Resultado: pasa / falla / bloqueado
Limitaciones y siguiente acción:
```
