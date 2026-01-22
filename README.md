# 🐦 Flappy – Lua + LÖVE2D

**Flappy** es una recreación del popular juego **Flappy Bird**, desarrollada en **Lua** usando el framework **LÖVE2D**.  
El objetivo principal fue practicar lógica de juegos 2D en tiempo real, sistemas de estados, y detección de colisiones. :contentReference[oaicite:1]{index=1}

---

## 🎮 ¿Cómo se juega?

- Controlás un pájaro que se desplaza horizontalmente.
- Cada vez que presionás la tecla de acción, el pájaro “flapea” hacia arriba.
- El jugador debe esquivar los obstáculos (tubos) para acumular puntos.
- La partida termina si el pájaro colisiona con un tubo o el suelo.

---

## 🧱 Estructura del proyecto

Flappy/
├─ main.lua # Entrada principal del juego
├─ states/ # Estados del juego
│ ├─ (states .lua files) # Ej: TitleScreenState, PlayState, ScoreState
├─ Bird.lua # Lógica de la entidad jugador
├─ Pipe.lua # Obstáculos independientes
├─ PipePair.lua # Pares de tubos generados
├─ StateMachine.lua # Máquina de estados para control de pantallas
├─ class.lua # Biblioteca pequeña de clases
├─ push.lua # Librería para resolución virtual
├─ graphics/.png # Sprites y assets visuales
├─ sounds/.wav/.mp3 # Sonidos y música
├─ fonts/*.ttf # Tipografías utilizadas
└─ (otros archivos multimedia)

yaml
Copy code

> La estructura modular permite separar responsabilidades entre entidades, estados y utilidades. :contentReference[oaicite:2]{index=2}

---

## 🛠️ Tecnologías usadas

- **Lenguaje:** Lua  
- **Framework:** LÖVE2D (motor de juegos 2D)  
- **Organización:** Modular, con separación de estados de juego

---

## 📦 Cómo ejecutar

### Requisitos

1. Tener instalado **LÖVE2D**  
   👉 https://love2d.org/

### Pasos

```bash
git clone https://github.com/Mat-Indaco/Flappy.git
cd Flappy
love .
¡El juego debería comenzar automáticamente! 🎉

🧠 Arquitectura técnica
🟡 Máquina de estados
El juego utiliza una State Machine para controlar el flujo entre diferentes pantallas (inicio, juego activo, score). Esto permite:

Separar lógica de cada pantalla

Facilitar la transición entre modos
(pantalla de título → juego → score) 
love2d.org

🔹 Entidades principales
Bird.lua – Control del pájaro (posición, velocidad, input)

Pipe.lua / PipePair.lua – Generación y movimiento de obstáculos

StateMachine.lua – Manejador de estados y transiciones

class.lua – Biblioteca de OOP mínima (creación de clases)

⚙️ Mecánicas clave
Game Loop (LÖVE2D)

love.load() inicializa recursos

love.update(dt) actualiza lógica

love.draw() renderiza cada frame

Física simple

Gravedad constante aplicada al pájaro

Rebote e impulso hacia arriba con input

Colisiones

Bounding boxes para detectar choque entre pájaro y tubos

Generación de obstáculos

Los tubos se generan a intervalos con alturas variables
(la lógica modular facilita ajustes futuros)

📈 Posibles mejoras
Añadir contador de puntos persistentes

Menús interactivos más complejos

Dificultad progresiva

Animación y efectos avanzados

Soporte táctil o versión exportable

📌 Autor
Mat
