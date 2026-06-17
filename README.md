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
| # | Requisito | Justificación |
|---|---|---|
| R1 | El juego deberá mostrar un tablero vacío antes de que comience una nueva partida. | Condición fundamental de inicio. |
| R2 | El tablero del juego deberá consistir en una cuadrícula con un ancho de 10 celdas y una altura de 24 celdas. | Define la estructura base indispensable del juego. |
| R3 | El juego deberá colocar una nueva pieza tetromino actual en la parte superior y en el centro del tablero cuando comience el juego. | Mecánica principal de generación de piezas. |
| R4 | El jugador deberá poder mover el tetromino actual una celda hacia la izquierda, derecha o abajo a la vez. | Control básico e indispensable del jugador. |
| R5 | El jugador deberá poder rotar el tetromino actual en unidades de 90 grados. | Mecánica esencial para la estrategia de Tetris. |
| R6 | El juego deberá permitir que el tetromino actual caiga lentamente (después de un tiempo determinado en milisegundos). | Bucle central del desafío de tiempo. |
| R7 | El juego no deberá permitir que el tetromino actual se mueva (parcialmente) fuera del tablero. | Lógica básica de límites del juego. |
| R8 | El juego no deberá permitir que el tetromino actual se rote (parcialmente) fuera del tablero. | Evita errores de posicionamiento. |
| R9 | El juego no deberá permitir que el tetromino actual se solape (parcialmente) con otros bloques ya fijados en el tablero del juego. | Base del sistema de colisiones. |
| R10 | El juego deberá fijar el tetromino actual cuando caiga o se mueva hacia abajo hasta el fondo del tablero del juego. | Transición necesaria del estado de la pieza. |
| R11 | El juego deberá fijar el tetromino actual cuando caiga o se mueva hacia abajo sobre uno o más bloques fijados en el tablero. | Lógica indispensable de apilamiento. |
| R12 | El juego no deberá permitir que un tetromino y sus bloques se muevan cuando estén fijados en el tablero. | Consistencia del tablero. |
| R13 | El juego deberá eliminar una o más filas de bloques en el tablero cuando una fila esté completamente llena de bloques. | El objetivo central del juego. |
| R14 | El juego deberá desplazar hacia abajo todos los bloques en las filas por encima de una fila que se haya eliminado. | Física básica tras completar el objetivo. |
| R15 | El juego deberá colocar un nuevo tetromino en la parte superior y en el centro del tablero después de que el tetromino actual se haya fijado. | Continuidad del bucle del juego. |
| R16 | El jugador perderá cuando se coloque inicialmente un nuevo tetromino en una posición del tablero que ya tenga uno o más bloques. | Condición esencial de fin de juego (Game Over). |
### Should Have (Debería Tener)
| # | Requisito | Justificación |
|---|---|---|
| R17 | El jugador deberá poder iniciar una nueva partida de Tetris. | Gestión esperada del flujo del sistema. |
| R18 | El jugador deberá poder detener una partida de Tetris que esté en progreso. | Control necesario sobre la sesión de juego. |
| R19 | El juego deberá finalizar una partida cuando el jugador pierda o la detenga. | Cierre correcto del ciclo de ejecución. |
| R20 | El juego deberá asignar un color brillante elegido al azar a cada tetromino. | Estándar visual para distinguir piezas fácilmente. |
| R21 | El juego deberá iniciar y mostrar la puntuación del jugador en 0. | Base para el sistema de recompensas. |
| R22 | El juego deberá tener múltiples niveles, y comenzará en el nivel número 1 al inicio del juego. | Proporciona progresión y reto a largo plazo. |
| R23 | El juego deberá llevar un registro de la puntuación... (sistema original de Nintendo). | Gamificación e incentivo estándar de Tetris. |
| R24 | El juego deberá llevar un registro del número de dobles, triples y tetrises limpiados. | Feedback detallado sobre el rendimiento. |
| R25 | El juego deberá mostrar, para cada nivel, el número de filas que se deben limpiar para avanzar. | Claridad sobre el objetivo inmediato. |
| R26 | El juego deberá aumentar el intervalo de tiempo en el que el tetromino actual cae automáticamente al avanzar de nivel. | Escala la dificultad progresivamente. |
| R27 | El juego deberá mostrar una vista previa del próximo tetromino. | Herramienta estratégica clásica y esperada. |
| R28 | El juego deberá limpiar el tablero cuando la partida haya sido detenida. | Restablece el estado de forma limpia. |
| R29 | El juego deberá mostrar las estadísticas del juego del jugador después de perder una partida. | Retrolimentación final de la partida. |
| R30 | El juego deberá reiniciar la puntuación y otras estadísticas cuando una partida finalice. | Prepara el sistema para un nuevo intento. |
| R31 | El juego deberá mostrar una rejilla visible en el tablero. | Mejora significativamente la experiencia de usuario (UX). |
### Could Have (Podría Tener)
| # | Requisito | Justificación |
|---|---|---|
| C1 | El juego deberá permitir al jugador pausar la partida en cualquier momento. | Comodidad extra para el usuario, no crítica. |
| C2 | El juego deberá incluir efectos de sonido para las acciones del jugador y eventos del juego. | Mejora la inmersión, pero el juego funciona sin ellos. |
### Won't Have (No Tendrá)
| # | Requisito | Justificación |
|---|---|---|
| W1 | El juego deberá mostrar una animación o efecto visual cuando se complete una línea. | Trabajo estético adicional fuera del alcance inicial. |
| W2 | El juego deberá proporcionar una opción para ajustar la velocidad de caída del tetromino. | Altera la curva de dificultad estándar diseñada. |
| W3 | El juego deberá permitir al jugador personalizar las teclas o controles utilizados para jugar. | Complejidad técnica extra evitable en la primera versión. |
| W4 | El juego deberá tener un sistema de clasificación o marcadores para los mejores puntajes. | Requiere persistencia de datos (base de datos/archivos) innecesaria por ahora. |
| W5 | El juego deberá incluir una opción para guardar y cargar partidas en curso. | Las partidas de Tetris son rápidas; el esfuerzo técnico no justifica el valor. |
| W6 | El juego deberá contar con un modo de juego multijugador, ya sea en línea o en un mismo dispositivo. | Cambia drásticamente el alcance y la arquitectura del proyecto. |
| W7 | El juego deberá ser compatible con diferentes plataformas o dispositivos (consolas, móviles). | Desarrollo limitado al entorno/plataforma objetivo principal actual. |

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
C4Component
    title Diagrama C4 Component — Motor interno del juego Tetris
    Container_Boundary(tetrisApp, "Aplicación del Juego (Interfaz de Usuario)") {
        Component(inputManager, "Gestor de Entrada de Teclado", "Módulo JS / Event Listener", "Captura eventos de teclado (mover izquierda, derecha, abajo, rotar) y los traduce en comandos. Solo procesa entrada si la partida está activa (R4, R5).")
        Component(gravityEngine, "Motor de Caída y Gravedad", "Módulo JS / setInterval", "Ejecuta el game loop. Hace caer el tetromino activo automáticamente según el intervalo del nivel actual. Aumenta la velocidad al subir de nivel (R6, R26).")
        Component(boardController, "Controlador del Tablero", "Módulo JS / Matriz 10x24", "Núcleo del juego. Gestiona la matriz de juego (R2). Valida movimientos y rotaciones (R7, R8, R9). Fija tetrominós (R10, R11, R12). Elimina filas completas (R13, R14). Detecta derrota (R16).")
        Component(scoreRenderer, "Renderizador del Puntaje", "Módulo JS / DOM Updater", "Muestra y actualiza la puntuación (R21, R23), nivel actual (R22), conteo de dobles, triples y tetrises (R24), filas necesarias para avanzar (R25) y estadísticas al perder (R29).")
    }
    Person(player, "Jugador", "Interactúa con el juego mediante el teclado")
    System_Ext(localStorage, "Almacenamiento Local", "Guarda configuraciones y puntajes máximos")
    Rel(player, inputManager, "Pulsa teclas de movimiento y rotación")
    Rel(inputManager, boardController, "Envía comandos: mover / rotar tetromino")
    Rel(gravityEngine, boardController, "Solicita descenso automático en cada tick")
    Rel(boardController, scoreRenderer, "Notifica filas eliminadas y nivel alcanzado")
    Rel(scoreRenderer, localStorage, "Persiste puntaje máximo al finalizar la partida")
```

---

## Nivel 4 — Diagrama Dinámico (C4Dynamic)

```mermaid
sequenceDiagram
    actor Jugador
    participant GEK as Gestor de Entrada<br/>de Teclado
    participant CT as Controlador<br/>del Tablero
    participant MCG as Motor de Caída<br/>y Gravedad
    participant RP as Renderizador<br/>del Puntaje
    Jugador->>GEK: Pulsa tecla ROTAR (↑ / Z)
    GEK->>GEK: Valida que la partida esté activa
    GEK->>CT: enviarComando(ROTAR)
    CT->>CT: Calcula nueva orientación del tetromino (90°)
    CT->>CT: Valida que no salga del tablero (R7, R8)
    CT->>CT: Valida que no solape bloques fijos (R9)
    alt Rotación válida
        CT->>CT: Aplica nueva orientación al tetromino activo
        CT-->>GEK: OK
    else Rotación inválida
        CT-->>GEK: RECHAZADO (sin cambios)
    end
    GEK-->>Jugador: Visualiza tetromino rotado (o sin cambio)
    Note over CT, MCG: El game loop de gravedad sigue corriendo en paralelo
    MCG->>CT: tick() — solicita descenso automático
    CT->>CT: Valida si puede bajar una celda
    alt Puede bajar
        CT->>CT: Mueve tetromino una celda hacia abajo
    else No puede bajar — colisión inferior
        CT->>CT: Fija tetromino en el tablero (R10, R11)
        CT->>CT: Detecta y elimina filas completas (R13, R14)
        CT->>RP: notificarFilasEliminadas(cantidad, nivelActual)
        RP->>RP: Calcula puntuación (sistema Nintendo R23)
        RP->>RP: Actualiza nivel, dobles, triples, tetrises (R24, R25)
        RP-->>CT: OK
        CT->>CT: Solicita nuevo tetromino (R15)
        CT->>CT: Verifica condición de derrota (R16)
    end
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