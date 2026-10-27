# 09 — Interfaz y controles

Estado: propuesta; mapas definitivos se ajustan con pruebas.

## Pantallas

Carga con errores recuperables; menú principal; taller; conducción; pausa/opciones; diálogo breve; cierre de desafío; gestión de diseños y respaldo.

El taller muestra catálogo, selección y conexión. Durante conducción, priorizar objetivo, ayuda de recuperación y datos relevantes. Evitar un HUD de telemetría lleno de información de desarrollo.

## Acciones por contexto

| Acción | Teclado/ratón propuesto | Contexto |
| --- | --- | --- |
| Acelerar / frenar / dirigir | WASD o flechas | Conducción |
| Recuperar | R | Conducción; con pequeño bloqueo contra repetición |
| Pausa / cancelar | Escape | Según pantalla |
| Seleccionar / colocar | Clic izquierdo | Taller |
| Orbitar | Arrastre con botón secundario | Taller |
| Zoom | Rueda del ratón | Taller |
| Rotar pieza | Q / E | Taller |
| Eliminar selección | Supr | Taller |
| Deshacer / rehacer | Ctrl+Z / Ctrl+Y | Taller |
| Probar | Botón visible | Taller |

No reutilizar un atajo oculto para acciones incompatibles en la misma pantalla. Menús no deben acelerar el vehículo. Limpiar entradas al perder foco y al cambiar de modo.

Mando: objetivo secundario tras teclado/ratón; conducción analógica y navegación de menús. No declarar soporte sin probar un mando real. Pantallas táctiles fuera del alcance inicial.

## Accesibilidad

Texto legible y escalable, contraste suficiente, señales de conexión que no dependan solo del color, subtítulos de diálogos y volumen separado para música/efectos. Reducir sacudida de cámara; evitar destellos innecesarios. Usar botones HTML con foco y etiquetas donde aplique.

No exigir maniobras cronometradas para aprender el constructor. Mostrar los controles actuales dentro del juego. Evaluar reasignación de teclas antes de publicación, según pruebas y alcance.

## Mensajes

«La pieza no tiene conexión», «Este diseño supera el límite de piezas» y «No se pudo guardar; puedes exportar una copia». No mostrar errores de WASM o stacks como texto principal al jugador; conservar detalles en diagnóstico.

## Pruebas de uso

Ver a jugadores colocar, borrar, recuperar, pausar y retomar sin explicación verbal continua. Registrar errores de clic, confusiones de cámara y si descubren cómo volver a editar. Probar pérdida de foco durante aceleración y cierre de diálogo con la misma tecla de interacción.

Ver [estados](diagramas/02-estados.md).
