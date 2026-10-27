# Diagrama 03 — Edición y ensamblaje

Estado: contrato propuesto de F1/F2.

```mermaid
flowchart TD
    A["Seleccionar pieza"] --> B["Previsualizar socket y rotacion"]
    B --> C{"Conexion y espacio validos"}
    C -->|No| D["Mostrar motivo"]
    D --> B
    C -->|Si| E["Aplicar comando reversible"]
    E --> F["Actualizar borrador e historial"]
    F --> G{"Probar"}
    G -->|No| A
    G -->|Si| H["Validar plano completo"]
    H --> J{"Plano valido"}
    J -->|No| K["Mostrar errores del diseno"]
    K --> A
    J -->|Si| L["Agrupar estructura rigida"]
    L --> M["Crear cuerpos y colisionadores"]
    M --> N["Crear ruedas y articulaciones necesarias"]
    N --> O{"Ensamblaje correcto"}
    O -->|No| Q["Liberar recursos parciales y conservar borrador"]
    Q --> A
    O -->|Si| R["Aparecer en punto seguro"]
    R --> S["Conducir"]
    S --> T["Volver al taller y liberar simulacion"]
    T --> A
```

El historial se aplica a datos. Un ensamblaje fallido no debe dejar cuerpos huérfanos ni cambiar el plano guardado. El editor no recupera el diseño leyendo posiciones de mallas después de conducir.

Ver [constructor](../06-constructor-de-vehiculos.md).
