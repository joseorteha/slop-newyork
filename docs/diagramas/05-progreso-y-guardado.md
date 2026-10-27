# Diagrama 05 — Progreso y persistencia

Estado: diseño propuesto.

```mermaid
sequenceDiagram
    participant W as Trigger del mundo
    participant M as Sistema de misiones
    participant S as Estado de partida
    participant G as Repositorio de guardado
    participant D as IndexedDB
    participant U as Interfaz
    W->>M: evento con ID y contexto
    M->>S: consultar objetivo y estado
    alt objetivo ya completado
        M-->>W: ignorar efecto duplicado
    else objetivo valido
        M->>S: completar y conceder desbloqueo una vez
        S->>G: snapshot versionado coherente
        G->>G: validar
        G->>D: transaccion de progreso y desbloqueos
        alt escritura correcta
            D-->>G: commit
            G-->>U: guardado confirmado
        else almacenamiento no disponible
            D-->>G: error
            G-->>U: aviso y opcion de respaldo
        end
    end
```

La interfaz diferencia progreso en memoria y persistencia confirmada. Al cargar, validar y migrar antes de sustituir la partida activa. Reintentar una escritura no debe duplicar la recompensa. No depender del cierre de pestaña para terminar una transacción.

Ver [datos](../11-datos-guardado-y-versionado.md).
