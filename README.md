# Gym Final — Rutinas del crew

Segunda generación de la app de gym del crew. Ya no hay rutinas estáticas: cada
persona arma y edita la suya, con un catálogo completo de ejercicios y macros
calculados por peso.

## Qué tiene

- **Rutina Test**: una rutina de ejemplo (empuje / jalón / pierna) para probar
  todo — checks, edición, series, animaciones. Se puede modificar y restaurar.
- **Creador de rutinas** («Mis rutinas»): eliges nombre y cantidad de días
  (1–7), y luego armas cada día con ejercicios del catálogo. Cada día tiene
  etiqueta y título renombrables; los ejercicios se agregan, quitan, reordenan
  y sus series se editan al tocarlas. Las rutinas se pueden renombrar y
  eliminar.
- **Catálogo de 1299 ejercicios por grupo muscular** (pecho, espalda, hombros,
  brazos, antebrazos, piernas, pantorrillas, core, cardio), con buscador. Cada
  ejercicio tiene animación GIF, músculo objetivo, equipamiento e instrucciones
  paso a paso en español, y un flujo para agregarlo a cualquier rutina y día.
- **Macros** con peso editable, recalculados al instante:
  - Proteína = peso × 2 (g)
  - Calorías = proteína × 14 (kcal)
  - Grasas = peso × 0.7 (g)
  - Carbohidratos = (calorías − proteína×4 − grasas×9) ÷ 4 (g)
  - *Pendiente: opciones de comidas para cumplir los macros.*
- Checks diarios por ejercicio con celebración al completar el día, cronómetro
  de descansos y PWA instalable (igual que la app original).

## Estructura

- `index.html` — toda la app (vanilla JS, sin dependencias)
- `data/ejercicios.js` — catálogo generado desde el dataset (solo campos
  necesarios + instrucciones en español, filtrado a equipamiento de gym real)
- `sw.js`, `manifest.webmanifest`, íconos — PWA

## Datos y créditos

Ejercicios del dataset [hasaneyldrm/exercises-dataset](https://github.com/hasaneyldrm/exercises-dataset)
(MIT + términos de medios). Las imágenes y GIFs son **© [Gym visual](https://gymvisual.com/)**,
redistribuidos con permiso a 180×180 con atribución; la app los enlaza
directamente desde el repositorio del dataset y muestra la atribución.

La persistencia (rutinas, pesos, checks) es `localStorage` del navegador.
