# Diagrama 07 — Entidades de datos

Estado: modelo conceptual propuesto; no es un esquema de base de datos implementado.

```mermaid
erDiagram
    PART_DEFINITION ||--o{ PLACED_PART : define
    VEHICLE_BLUEPRINT ||--|{ PLACED_PART : contiene
    VEHICLE_BLUEPRINT ||--o{ CONNECTION : contiene
    PLACED_PART ||--o{ CONNECTION : participa
    SAVE_GAME ||--o{ VEHICLE_BLUEPRINT : conserva
    SAVE_GAME ||--o{ MISSION_PROGRESS : registra
    MISSION_DEFINITION ||--o{ MISSION_PROGRESS : define
    PART_DEFINITION {
        string id PK
        int revision
        float massKg
    }
    PLACED_PART {
        string instanceId PK
        string definitionId FK
        string position
        string rotation
    }
    VEHICLE_BLUEPRINT {
        string id PK
        int schemaVersion
        string rootPartId
    }
    CONNECTION {
        string partA
        string socketA
        string partB
        string socketB
    }
    SAVE_GAME {
        int schemaVersion
        string catalogVersion
        string activeBlueprintId
    }
    MISSION_DEFINITION {
        string id PK
    }
    MISSION_PROGRESS {
        string missionId FK
        string state
    }
```

Posición y rotación se muestran como campos conceptuales; en el contrato JSON son arrays numéricos. Una conexión siempre tiene dos extremos, cada uno con pieza y socket. La cardinalidad conceptual no sustituye la validación de conectividad, raíz única y ocupación de conectores.

Ver [contratos](../11-datos-guardado-y-versionado.md).
