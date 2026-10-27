# 07 — Físicas y conducción

Estado: Rapier aprobado como candidato principal; comportamiento por validar.

## Convenciones propuestas

Una unidad = un metro; masa en kg; tiempo en segundos; ángulos en radianes. Mundo con Y hacia arriba. Delante local del vehículo: +Z; derecha: +X. Blender requiere exportación que respete la conversión a estos ejes; no corregir cada modelo con offsets ocultos.

Rapier simula; Three.js representa. No conservar el controlador planar heredado sobre el vehículo nuevo.

## Cuerpos compuestos

Piezas estructurales conectadas rígidamente forman un cuerpo con varios colisionadores. La masa y su distribución deben reflejar lo construido. Evitar dar masa completa al cuerpo y repetirla accidentalmente en los colisionadores. Verificar centro de masa e inercia con diseños simétricos y asimétricos.

Reservar articulaciones para partes realmente móviles: remolque o brazo en expansión. No unir cada bloque con un joint rígido; incrementa costo y problemas numéricos.

## Ruedas y suspensión

Primer candidato: controlador por rayos de Rapier. Ajustar recorrido de suspensión, rigidez, amortiguamiento, radio, agarre, fuerza motriz, freno y ángulo de dirección. Posición y capacidades de las ruedas proceden del plano.

El modelo por rayos no reproduce todos los contactos laterales de una rueda. Probar bordillos, obstáculos angostos y terreno irregular antes de aceptarlo. No prometer físicas idénticas a Trailmakers.

La fuerza disponible y el frenado deben depender de la configuración. La distribución de peso debe importar sin exigir simulación automotriz profesional. Priorizar coherencia y diversión.

## Colisiones y estabilidad

Usar colisionadores simples/convexos para partes dinámicas. Reservar terreno estático más complejo cuando sea necesario. Definir grupos de colisión para evitar autocolisiones incorrectas. Evaluar CCD en objetos rápidos, no habilitarlo indiscriminadamente.

Paso inicial 60 Hz; evaluar subpasos y parámetros con pruebas. Detectar NaN/infinito y reiniciar con diagnóstico, sin sobrescribir el último plano válido.

Recuperación: trasladar a un punto seguro, poner orientación estable, limpiar velocidades y comprobar espacio libre. No reaparecer dentro de terreno o de un objeto.

## Presupuesto de ensayo

Un vehículo activo, hasta 40 piezas colocadas y articulaciones solo si son necesarias. Son límites de prueba ajustables, no rendimiento certificado. Repetir un recorrido de 60 s con configuraciones simétrica, pesada y asimétrica; repetir entrada/salida del taller para comprobar liberación.

## Agua, vuelo y destrucción

Flotación, resistencia del agua y empuje requieren fuerzas adicionales. El vuelo requiere sustentación/propulsión y control específicos. Roturas por esfuerzo necesitan topología y reconstrucción. Nada de esto queda resuelto por instalar Rapier; fuera de demo terrestre.

Ver [decisión 002](decisiones/002-fisica-modular.md), [pruebas](12-pruebas-y-rendimiento.md) y [fuentes](18-fuentes-y-glosario.md).
