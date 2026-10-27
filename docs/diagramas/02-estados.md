# Diagrama 02 — Estados del juego

Estado: propuesta. Cada transición debe limpiar entradas y recursos específicos.

```mermaid
stateDiagram-v2
    [*] --> Carga
    Carga --> Menu: recursos listos
    Carga --> ErrorRecuperable: fallo
    ErrorRecuperable --> Carga: reintentar
    Menu --> Taller: nueva partida o cargar
    Taller --> Validacion: probar
    Validacion --> Taller: diseno invalido
    Validacion --> Conduccion: ensamblaje correcto
    Validacion --> Taller: fallo y limpieza
    Conduccion --> Taller: volver a editar
    Conduccion --> Recuperacion: vuelco o atasco
    Recuperacion --> Conduccion: punto seguro
    Conduccion --> Resultado: desafio completado
    Resultado --> Conduccion: continuar
    Resultado --> Taller: modificar
    Conduccion --> Pausa: pausar
    Taller --> Pausa: pausar
    Pausa --> Conduccion: reanudar conduccion
    Pausa --> Taller: reanudar taller
    Pausa --> Menu: salir
```

Pausa recuerda el estado anterior; no elige arbitrariamente entre taller y conducción. El diagrama resume estados: diálogos modales pueden bloquear acciones sin crear una segunda simulación. Perder foco limpia entradas y detiene avance según política de pausa.

Ver [interfaz](../09-interfaz-y-controles.md).
