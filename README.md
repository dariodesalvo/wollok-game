# Maze Escape

Un juego de escape room desarrollado en [Wollok](https://www.wollok.org/) como trabajo práctico grupal de la materia 
"Paradigmas de programación" de la carrera de Ing. en Sistemas de la Facultad UTN FRBA.  
El jugador debe resolver una serie de puzzles encadenados en tres habitaciones para escapar antes de que se acabe el tiempo.

---

## Capturas

<img src="https://github.com/pdepmartestm/2021-wgame-grupo-3/blob/master/screenshot1.jpg" alt="Gameplay screenshot" width="600">

---

## Características

- **3 niveles** con puzzles independientes y encadenados
- **Sistema de inventario** para recoger y usar objetos
- **Contador regresivo** con presión de tiempo
- **Pistas contextuales** integradas en el escenario
- **Banda sonora** ambiental

---

## Cómo jugar

| Tecla | Acción |
|-------|--------|
| `↑ ↓ ← →` | Mover al personaje |
| `Espacio` | Interactuar con objetos cercanos |

Explora cada habitación buscando objetos que puedas recoger o examinar. Algunos objetos necesitan combinarse o usarse en el orden correcto para avanzar.

### Niveles

**Nivel 1 — La primera habitación**
Encuentra la llave correcta entre las cajas y úsala para abrir la puerta. Interactúa con el sombrero al inicio: activará la música y te dará una pista.

**Nivel 2 — La habitación con cuadros**
Resuelve una cadena de puzzles: revisa la cama, abre los cuadros y el armario en el orden correcto hasta conseguir la llave de la puerta.

**Nivel 3 — El panel de botones**
Presiona los cuatro botones de colores en el orden correcto y confirma la secuencia. El botón de confirmación muestra pistas en forma de versos si necesitás ayuda.

---

## Instalación y ejecución

### Requisitos

- [Wollok IDE](https://www.wollok.org/instalacion/) (versión 1.x)

### Pasos

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/pdepmartestm/2021-wgame-grupo-3.git
   ```
2. Abrir el proyecto en Wollok IDE (`File → Open Project`).
3. Ejecutar el archivo `src/juego.wpgm`.

---

## Estructura del proyecto

```
src/
├── juego.wlk        # Punto de entrada, configuración del juego y niveles
├── juego.wpgm       # Programa principal (runner)
├── Escenario.wlk    # Clases base: Nivel, Element, PickUp, Puerta; objetos del nivel 1
├── nivel2.wlk       # Objetos y lógica del nivel 2
├── nivel3.wlk       # Objetos, botones y lógica del nivel 3
├── player.wlk       # Clase Player: movimiento e inventario
├── timer.wlk        # Temporizador regresivo
└── tests.wtest      # Tests unitarios
assets/              # Imágenes y audio del juego
```

---

## Diseño orientado a objetos

El juego aplica los principios de POO trabajados en la materia:

- **Herencia**: `PickUp` y `Puerta` extienden `Element`; `Button` y `confirmButton` también heredan de `Element`.
- **Polimorfismo**: todos los objetos del escenario responden a `collision()` e `interact()`, permitiendo que el motor del juego los trate de forma uniforme.
- **Encapsulamiento**: cada nivel gestiona sus propios objetos; el inventario del jugador es opaco para el escenario.
- **Objetos bien conocidos (WKO)**: `sombrero`, `cuadro1`, `cuadro2`, `armario`, `cama`, `door3` y `secuences` son objetos singleton con comportamiento propio.

---

## Equipo

| Nombre | GitHub |
|--------|--------|
| Carretto, Julián | — |
| García, Nicolás | — |
| Desalvo, Darío | [@dariodesalvo](https://github.com/dariodesalvo) |

---

## Licencia

Distribuido bajo la licencia [MIT](https://opensource.org/licenses/MIT).
