# El último taller — documentación del proyecto

Nombre y argumento provisionales. Dirección aprobada: aventura de construcción de vehículos y exploración, para computadora y navegador, conservando Three.js.

## Estado real

Esta entrega documenta el diseño y la ejecución futura. El código ejecutable del fork sigue siendo Slop New York. No están implementados el constructor, Rapier, TypeScript, Bun, las misiones ni el mundo nuevo. No se ha publicado la aventura ni modificado una carpeta local de Windows desde GitHub.

Base inspeccionada: [1a1cfd85](https://github.com/joseorteha/slop-newyork/commit/1a1cfd85bd3bc4d866afbbb56caf1a3646efc54a). Fecha de documentación: 26 de octubre de 2026, America/Mexico_City.

## Lectura recomendada

1. [Contexto y objetivos](01-contexto-y-objetivos.md).
2. [Diseño del juego](02-diseno-del-juego.md).
3. [Alcance y fases](03-alcance-y-fases.md).
4. [Arquitectura](05-arquitectura-tecnica.md).
5. [Backlog de ejecución](17-backlog.md).

## Índice completo

| Documento | Contenido |
| --- | --- |
| [01 — Contexto](01-contexto-y-objetivos.md) | Objetivo, restricciones y acuerdos |
| [02 — Diseño](02-diseno-del-juego.md) | Ciclo jugable, piezas, historia y experiencia |
| [03 — Fases](03-alcance-y-fases.md) | Demo, entregables y puertas de validación |
| [04 — Auditoría del origen](04-analisis-del-repositorio-original.md) | Qué existe y qué reutilizar |
| [05 — Arquitectura](05-arquitectura-tecnica.md) | Módulos, dependencias y ciclo de ejecución |
| [06 — Constructor](06-constructor-de-vehiculos.md) | Conexiones, edición y ensamblaje |
| [07 — Física](07-fisicas-y-conduccion.md) | Cuerpos, ruedas, fuerzas y estabilidad |
| [08 — Mundo e historia](08-mundo-historia-y-misiones.md) | Diseño de niveles y misiones |
| [09 — Interfaz](09-interfaz-y-controles.md) | Flujos, controles y accesibilidad |
| [10 — Recursos](10-arte-modelos-y-audio.md) | Producción artística, medidas y exportación |
| [11 — Datos](11-datos-guardado-y-versionado.md) | Contratos, validación y persistencia |
| [12 — Pruebas](12-pruebas-y-rendimiento.md) | Escenarios, métricas y compatibilidad |
| [13 — Windows y Git](13-desarrollo-en-windows.md) | Carpeta permitida y flujo de trabajo |
| [14 — Publicación](14-compilacion-y-publicacion.md) | Compilación, HTTPS y versiones |
| [15 — Licencias](15-licencias-y-atribuciones.md) | Código y recursos de terceros |
| [16 — Riesgos](16-riesgos-y-pendientes.md) | Incertidumbres y criterios de resolución |
| [17 — Backlog](17-backlog.md) | Tareas ordenadas con aceptación |
| [18 — Fuentes](18-fuentes-y-glosario.md) | Referencias oficiales y vocabulario |
| [19 — Validación](19-validacion-documental.md) | Comprobaciones y límites de esta entrega |

## Decisiones y diagramas

- [Registro de decisiones](decisiones/README.md): decisiones 001–004.
- [Arquitectura](diagramas/01-arquitectura.md).
- [Estados del juego](diagramas/02-estados.md).
- [Ensamblaje](diagramas/03-construccion.md).
- [Ciclo físico](diagramas/04-simulacion.md).
- [Progreso y guardado](diagramas/05-progreso-y-guardado.md).
- [Distribución web](diagramas/06-publicacion.md).
- [Entidades de datos](diagramas/07-datos.md).
- [Ejemplo de plano](ejemplos/plano-vehiculo.v1.json).

Los diagramas Mermaid son editables y GitHub puede representarlos. Son diseños propuestos, no comprobantes de implementación.

## Mantenimiento

Usar los estados **Acordado**, **Propuesto**, **Por validar**, **Implementado** y **Verificado**. Solo declarar Implementado con código identificable y Verificado con evidencia del entorno y la prueba. Cada cambio de contrato debe actualizar sus consumidores, ejemplo y decisión relacionada. Registrar resultados reales en el documento de pruebas; no convertir objetivos en mediciones.

La siguiente actividad es F0-01 del backlog. No empezar por cambiar todo Manhattan ni producir una región completa.
