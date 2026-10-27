# ADR 001 — Mantener Three.js y usar TypeScript

Estado: acordado, integración por validar.

## Contexto

El usuario quiere conservar el motor y construir una aventura modular para navegador/PC. El origen usa Three.js, WebGPURenderer y TSL. Reescribir en otro motor pierde parte del trabajo aprovechable.

## Decisión

Mantener Three.js. Escribir nuevos sistemas de juego en TypeScript, con migración selectiva de JS. Usar Rapier WASM: el juego aprovecha Rust dentro de esa dependencia sin requerir módulos Rust propios.

## Alternativas

Todo en Rust/Bevy cambia el motor. Reescribir físicas propias en Rust añade trabajo que no valida el atractivo del juego. Mantener todo en JS es viable, pero TypeScript ayuda a contratos de piezas y guardados.

## Consecuencias

Dos mundos de ejecución JS/WASM que deben sincronizarse, una resolución coherente de Three.js y costo de migración acotado. No esperar mejoras gráficas automáticas por usar Rust.

## Evidencia y revisión

Revisar tras F0/F1 si la integración impide objetivos medidos. Añadir Rust propio solo ante un cálculo identificado; no por tendencia ni para cambiar la etiqueta tecnológica.
