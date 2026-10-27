# Diagrama 04 — Paso fijo y representación

Estado: secuencia propuesta; el bucle actual del fork todavía es diferente.

```mermaid
sequenceDiagram
    participant B as Navegador
    participant A as App
    participant I as Entrada
    participant P as Rapier
    participant M as Misiones
    participant R as Three.js
    B->>A: frame y tiempo transcurrido
    A->>A: acotar delta y actualizar acumulador
    A->>I: leer acciones del contexto
    loop mientras haya paso fijo y presupuesto
        A->>P: aplicar controles y fuerzas
        A->>P: simular un paso
        P-->>A: poses y contactos
        A->>M: eventos del paso
        M-->>A: cambios de progreso
        A->>A: descontar paso del acumulador
    end
    A->>R: interpolar poses y actualizar camara
    A->>R: dibujar escena
```

Punto inicial: 60 Hz físicos, con límite de subpasos por definir y registrar en F0. Tras suspensión, evitar ponerse al día de forma ilimitada. Las misiones temporizadas usan tiempo de juego; en pausa no avanzan. Guardado se programa por eventos y no bloquea cada paso.

Ver [física](../07-fisicas-y-conduccion.md) y [pruebas](../12-pruebas-y-rendimiento.md).
