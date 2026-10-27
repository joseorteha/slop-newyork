# 05 — Arquitectura técnica

Estado: arquitectura objetivo. No describe código nuevo ya implementado.

## Componentes y límites

| Módulo propuesto | Responsabilidad | No debe asumir |
| --- | --- | --- |
| app | Estados, composición, carga y ciclo | Reglas particulares de una pieza |
| domain/vehicles | Catálogo, planos y validación | Objetos Three.js o handles Rapier persistidos |
| builder | Comandos de edición y selección | Movimiento físico durante edición |
| physics | Ensamblaje físico, paso y contactos | Recompensas o interfaz |
| rendering | Escena, materiales y presentación | Autoridad sobre posición simulada |
| world | Terreno, puntos de recuperación y triggers | Datos de progreso incrustados en mallas |
| story | Objetivos, eventos y desbloqueos | Nombres visuales como IDs de misión |
| persistence | Validación, migraciones y transacciones | Acceso al DOM |
| ui/input/audio | Presentación, acciones y sonido | Escribir cuerpos físicos directamente |

Dependencias: dominio puro al centro; adaptadores para Three.js, Rapier y almacenamiento. App conecta sistemas y traduce eventos. No introducir un ECS completo en F0 sin justificarlo.

## Organización futura

```text
src/
  app/ domain/ builder/ physics/ rendering/
  world/ story/ persistence/ ui/ input/ audio/
public/
assets-source/
tests/
docs/
```

Esta estructura aún no existe. Conservar la entrada original durante la migración y añadir el prototipo como entrada independiente. No convertir todos los JS heredados antes de obtener una prueba jugable.

## Tecnología

Three.js y TSL para gráficos; TypeScript para juego; Rapier 3D WASM para física; Bun para herramientas. Versiones exactas se fijarán tras F0 en manifiesto y lockfile. No mezclar instancias distintas de Three.js a través de import map y bundler. Si se conserva el commit upstream, usar una resolución coherente para core, TSL y addons.

Interfaz inicial HTML/CSS. No se necesita React, backend, login ni IA generativa en partida. Guardado local e importación/exportación de archivos.

## Contratos de integración propuestos

- Input produce acciones normalizadas con contexto taller/conducción/menú.
- Builder produce un VehicleBlueprint validado.
- VehicleAssembler crea handles temporales y una correspondencia ID de pieza → representación.
- Physics emite contactos y poses; Rendering consume poses.
- MissionSystem procesa eventos identificados y emite cambios de progreso.
- SaveRepository persiste datos validados y versionados.

No son APIs públicas implementadas. Tipos y nombres finales se fijan en F1/F2.

## Ciclo

Usar acumulador de tiempo con paso fijo inicial de 1/60 s. Limitar subpasos por frame y descartar exceso tras suspensión prolongada; no intentar simular minutos al volver a la pestaña. Interpolar poses para dibujar. Al pausar, congelar simulación y temporizadores de misión. Reiniciar entradas al perder foco.

Mantener simulación inicialmente en el hilo principal; introducir Worker solo ante mediciones y un contrato de mensajes. Rust propio tampoco es requisito inicial.

Al descargar una zona o reconstruir un vehículo, liberar cuerpos, joints, listeners y recursos gráficos sin duplicados. Carga fallida debe terminar en una pantalla recuperable.

Ver [diagrama](diagramas/01-arquitectura.md), [simulación](diagramas/04-simulacion.md) y [decisión 001](decisiones/001-motor-y-lenguajes.md).
