# 10 — Arte, modelos y audio

Estado: dirección propuesta; no hay recursos propios finales.

## Dirección visual

Taller costero de colores cálidos, piezas recuperadas con formas claras y vehículos pequeños con personalidad. Silueta y lectura de conexiones importan más que acumular detalles. La apariencia de una pieza debe comunicar su función.

Conservar Three.js no obliga a conservar la estética ni la geografía de Manhattan.

## Pipeline de piezas

1. Definir función, medidas, masa y conectores en catálogo.
2. Modelar en Blender con escala coherente.
3. Exportar GLB/glTF con materiales compatibles.
4. Comprobar orientación, pivote, transformaciones y conectores en visor.
5. Crear colisionadores simples separados de la malla visible.
6. Probar en constructor y pista antes de añadir variantes.

Mantener originales en assets-source y exportados en public cuando existan esas carpetas. Las definiciones de conectores deben validarse respecto al modelo, no copiarse manualmente en múltiples sistemas.

Convención propuesta: nombres de archivo minúsculos con guiones, identificadores estables separados del nombre traducido. Documentar dimensiones y eje frontal +Z del contrato de juego.

## Rendimiento

Compartir geometrías/materiales para piezas repetidas; evaluar instancing donde la selección lo permita. Evitar transparencias y materiales únicos sin necesidad. Probar compresión de mallas/texturas según soporte y costo de carga; no fijar herramientas de compresión antes de validarlas.

Tres perfiles iniciales de diseño: alto, medio y reducido. Reducir resolución interna, reflejos y sombras según mediciones. Calidad reducida debe conservar señales jugables y selección clara.

## Animación y cámara

Animar ruedas, suspensión visual y personaje según estado físico. Evitar animaciones que sugieran una conexión inexistente. Cámara con seguimiento suave y opciones para reducir movimiento; tratar oclusión y espacios estrechos.

## Audio

Confirmaciones discretas al colocar/conectar, error suave, motor que responda a aceleración/carga, impactos por intensidad y música que acompañe zonas. No disparar eventos de colisión repetidamente sin límite.

Iniciar contexto de audio tras interacción del usuario. Pausar o atenuar al perder foco. Separar música, efectos y diálogo en controles de volumen.

## Licencias

Cada recurso debe tener autor, origen, permiso y modificaciones registrados. No usar modelos, música, nombres ni interfaz de Trailmakers por ser referencia mecánica. Ver [atribuciones](15-licencias-y-atribuciones.md).
