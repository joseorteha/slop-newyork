# Diagrama 01 — Arquitectura objetivo

Estado: propuesto. Las flechas muestran intercambio o dependencia; no código ya conectado.

```mermaid
flowchart TD
    P["Jugador"] --> I["Entrada por contexto"]
    I --> APP["App y estados"]
    APP --> B["Constructor"]
    B --> V["Plano y validacion de dominio"]
    V --> A["Ensamblador"]
    A --> PH["Rapier WASM"]
    APP --> M["Misiones y progreso"]
    APP --> W["Mundo y triggers"]
    W --> M
    PH --> PO["Poses y contactos"]
    PO --> R["Three.js y TSL"]
    PO --> AU["Audio"]
    PO --> M
    V --> S["Repositorio de guardado"]
    M --> S
    S --> DB["IndexedDB y respaldo"]
    APP --> UI["Interfaz HTML y CSS"]
    M --> UI
    B --> UI
    R --> C["Canvas"]
```

El dominio de planos no conoce Rapier ni Three.js. El ensamblador crea recursos temporales. Física entrega poses; el renderizador no toma autoridad física. Misiones consumen eventos y actualizan datos de progreso.

Ver [arquitectura](../05-arquitectura-tecnica.md).
