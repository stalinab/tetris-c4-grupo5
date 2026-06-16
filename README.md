# ESCUELA POLITÉCNICA NACIONAL
### Facultad de Sistemas

**Integrantes:**
- ANRANGO STALIN
- ARÍZAGA SAMIRA
- BETANCOURT ALISON
- DÁVILA PAÚL
- RAMOS SEBASTIÁN
- SARASTI SEBASTIÁN

---

# Tetris con Modelo C4

**Institución:** Escuela Politécnica Nacional (EPN)

Este repositorio contiene la resolución de la actividad de Verificación y Validación en el Diseño, aplicando el modelo C4 sobre el sistema Tetris. Los diagramas fueron elaborados considerando los requisitos del documento "Tetris requisitos" bajo el enfoque MoSCoW, incluyendo únicamente los requisitos que el sistema **debe tener** (Must Have) y opcionalmente los que **debería tener** (Should Have).

---

## Tabla de Contenidos

- [Análisis MoSCoW](#análisis-moscow)
- [Nivel 1 — Diagrama de Contexto (C4Context)](#nivel-1--diagrama-de-contexto-c4context)
- [Nivel 2 — Diagrama de Contenedores (C4Container)](#nivel-2--diagrama-de-contenedores-c4container)
- [Nivel 3 — Diagrama de Componentes (C4Component)](#nivel-3--diagrama-de-componentes-c4component)
- [Nivel 4 — Diagrama Dinámico (C4Dynamic)](#nivel-4--diagrama-dinámico-c4dynamic)

---

## Análisis MoSCoW
### Must Have (Debe Tener)
| # | Requisito |
|---|---|
| R1 | El juego deberá mostrar un tablero vacío antes de que comience una nueva partida. |
| R2 | El tablero del juego deberá consistir en una cuadrícula con un ancho de 10 celdas y una altura de 24 celdas. |
| R3 | El juego deberá colocar una nueva pieza tetromino actual en la parte superior y en el centro del tablero cuando comience el juego. |
| R4 | El jugador deberá poder mover el tetromino actual una celda hacia la izquierda, derecha o abajo a la vez. |
| R5 | El jugador deberá poder rotar el tetromino actual en unidades de 90 grados. |
| R6 | El juego deberá permitir que el tetromino actual caiga lentamente (después de un tiempo determinado en milisegundos). |
| R7 | El juego no deberá permitir que el tetromino actual se mueva (parcialmente) fuera del tablero. |
| R8 | El juego no deberá permitir que el tetromino actual se rote (parcialmente) fuera del tablero. |
| R9 | El juego no deberá permitir que el tetromino actual se solape (parcialmente) con otros bloques ya fijados en el tablero del juego. |
| R10 | El juego deberá fijar el tetromino actual cuando caiga o se mueva hacia abajo hasta el fondo del tablero del juego. |
| R11 | El juego deberá fijar el tetromino actual cuando caiga o se mueva hacia abajo sobre uno o más bloques fijados en el tablero. |
| R12 | El juego no deberá permitir que un tetromino y sus bloques se muevan cuando estén fijados en el tablero. |
| R13 | El juego deberá eliminar una o más filas de bloques en el tablero cuando una fila esté completamente llena de bloques (es decir, se forme una línea horizontal de 10 bloques). |
| R14 | El juego deberá desplazar hacia abajo todos los bloques en las filas por encima de una fila que se haya eliminado. |
| R15 | El juego deberá colocar un nuevo tetromino en la parte superior y en el centro del tablero después de que el tetromino actual se haya fijado en el tablero (después de lo cual este nuevo tetromino se convierte en el tetromino actual). |
| R16 | El jugador perderá cuando se coloque inicialmente un nuevo tetromino en una posición del tablero que ya tenga uno o más bloques. |
### Should Have (Debería Tener)
| # | Requisito |
|---|---|
| R17 | El jugador deberá poder iniciar una nueva partida de Tetris. |
| R18 | El jugador deberá poder detener una partida de Tetris que esté en progreso. |
| R19 | El juego deberá finalizar una partida cuando el jugador pierda o la detenga. |
| R20 | El juego deberá asignar un color brillante elegido al azar a cada tetromino. |
| R21 | El juego deberá iniciar y mostrar la puntuación del jugador en 0. |
| R22 | El juego deberá tener múltiples niveles, y comenzará en el nivel número 1 al inicio del juego. |
| R23 | El juego deberá llevar un registro de la puntuación del jugador utilizando el sistema de puntuación original de Nintendo: Limpiar una fila individual agregará 40 * (número de nivel). Limpiar dos filas agregará 100 * (número de nivel). Limpiar tres filas agregará 300 * (número de nivel). Limpiar cuatro filas agregará 1200 * (número de nivel). |
| R24 | El juego deberá llevar un registro del número de dobles (dos filas a la vez), triples (tres filas a la vez) y tetrises (cuatro filas a la vez) limpiados. |
| R25 | El juego deberá mostrar, para cada nivel, el número de filas que se deben limpiar para avanzar al siguiente nivel. |
| R26 | El juego deberá aumentar el intervalo de tiempo en el que el tetromino actual cae automáticamente cuando el jugador avance al siguiente nivel. |
| R27 | El juego deberá mostrar una vista previa del próximo tetromino que se colocará en la parte superior y en el centro del tablero. |
| R28 | El juego deberá limpiar el tablero cuando la partida haya sido detenida. |
| R29 | El juego deberá mostrar las estadísticas del juego del jugador después de perder una partida. |
| R30 | El juego deberá reiniciar la puntuación del jugador y otras estadísticas del juego (nivel actual, número de dobles, triples y tetrises limpiados) cuando una partida finalice. |
| R31 | El juego deberá mostrar una rejilla visible en el tablero. |
### Could Have (Podría Tener)
| # | Requisito |
|---|---|
| C1 | El juego deberá permitir al jugador pausar la partida en cualquier momento. |
| C2 | El juego deberá incluir efectos de sonido para las acciones del jugador y eventos del juego. |
### Won't Have (No Tendrá)
| # | Requisito |
|---|---|
| W1 | El juego deberá mostrar una animación o efecto visual cuando se complete una línea. |
| W2 | El juego deberá proporcionar una opción para ajustar la velocidad de caída del tetromino. |
| W3 | El juego deberá permitir al jugador personalizar las teclas o controles utilizados para jugar. |
| W4 | El juego deberá tener un sistema de clasificación o marcadores para los mejores puntajes. |
| W5 | El juego deberá incluir una opción para guardar y cargar partidas en curso. |
| W6 | El juego deberá contar con un modo de juego multijugador, ya sea en línea o en un mismo dispositivo. |
| W7 | El juego deberá ser compatible con diferentes plataformas o dispositivos, como computadoras, consolas o dispositivos móviles. |

---

## Nivel 1 — Diagrama de Contexto (C4Context)

```mermaid

```

---

## Nivel 2 — Diagrama de Contenedores (C4Container)

```mermaid

```

---

## Nivel 3 — Diagrama de Componentes (C4Component)

```mermaid

```

---

## Nivel 4 — Diagrama Dinámico (C4Dynamic)

```mermaid

```

---

## 🖼️ Imágenes Exportadas

| Diagrama | Imagen |
|----------|--------|
| Nivel 1 — Contexto | `diagramas/nivel1-contexto.png` |
| Nivel 2 — Contenedores | `diagramas/nivel2-contenedor.png` |
| Nivel 3 — Componentes | `diagramas/nivel3-componente.png` |
| Nivel 4 — Dinámico | `diagramas/nivel4-dinamico.png` |

---
