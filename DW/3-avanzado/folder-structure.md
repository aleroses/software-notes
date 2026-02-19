# Estructura de carpetas

## Regla mental simple

> **Si un componente existe SOLO por el juego → `features/game`**  
> **Si puede reutilizarse o es UI genérica → `shared`**  
> **Si es lógica pura → `feature/game/logic`**  
> **Si controla estado del juego → `feature/game`**

Los *modales* **NO son algo especial**.
Son **componentes**, y viven donde viva la feature que los usa.

Estructura:

```txt
src/
├── app/
│   ├── App.tsx
│   └── main.tsx
│
├── features/
│   ├── game/
│   │   ├── components/
│   │   │   ├── Board.tsx
│   │   │   ├── Square.tsx
│   │   │   ├── WinnerModal.tsx
│   │   │   ├── GameModeModal.tsx
│   │   │   ├── LevelSelector.tsx
│   │   │   ├── CharacterSelector.tsx
│   │   │   └── MachineSelector.tsx
│   │   │
│   │   ├── modes/
│   │   │   ├── PlayerVsPlayer.tsx
│   │   │   └── PlayerVsComputer.tsx
│   │   │
│   │   ├── logic/
│   │   │   ├── checkWinner.ts
│   │   │   ├── winningCombinations.ts
│   │   │   ├── board.ts
│   │   │   ├── ai.ts
│   │   │   └── storage.ts
│   │   │
│   │   ├── game.types.ts
│   │   ├── gameReducer.ts
│   │   ├── GameContext.tsx
│   │   ├── GameProvider.tsx
│   │   └── index.ts
│
├── shared/
│   ├── components/
│   │   └── Logo.tsx
│   ├── constants.ts
│
├── assets/
│   ├── images/
│   │   ├── background/
│   │   ├── bowser.svg
│   │   ├── goomba.svg
│   │   ├── koopa.svg
│   │   ├── mario.svg
│   │   ├── pirana.svg
│   │   ├── racoon.svg
│   │   ├── star.svg
│   │   ├── toad.svg
│   │   └── question.gif
│   │
│   └── fonts/
│       └── DynaPuff_SemiCondensed-Bold.ttf
│
├── styles/
│   └── globals.css
```

---

## Mapeo exacto: de tu estructura actual

Componentes (`src/components`)

| Antes                   | Ahora                                            | Por qué                  |
| ----------------------- | ------------------------------------------------ | ------------------------ |
| `Square.jsx`            | `features/game/components/Square.tsx`            | Parte del tablero        |
| `WinnerModal.jsx`       | `features/game/components/WinnerModal.tsx`       | Modal del juego          |
| `GameModeModal.jsx`     | `features/game/components/GameModeModal.tsx`     | Controla flujo del juego |
| `LevelSelector.jsx`     | `features/game/components/LevelSelector.tsx`     | Regla del juego          |
| `CharacterSelector.jsx` | `features/game/components/CharacterSelector.tsx` | Lógica del juego         |
| `MachineSelector.jsx`   | `features/game/components/MachineSelector.tsx`   | Modo de juego            |
| `PlayerVsPlayer.jsx`    | `features/game/modes/PlayerVsPlayer.tsx`         | Es un modo               |
| `PlayerVsComputer.jsx`  | `features/game/modes/PlayerVsComputer.tsx`       | Es un modo               |
| `Logo.jsx`              | `shared/components/Logo.tsx`                     | UI reutilizable          |

👉 **Los modales NO van en una carpeta “modals”**
Van donde vive la feature que los necesita.

Lógica (`src/logic`)

| Antes                    | Ahora                                        |
| ------------------------ | -------------------------------------------- |
| `ai.js`                  | `features/game/logic/ai.ts`                  |
| `board.js`               | `features/game/logic/board.ts`               |
| `checkWinner.js`         | `features/game/logic/checkWinner.ts`         |
| `winningCombinations.js` | `features/game/logic/winningCombinations.ts` |
| `storage.js`             | `features/game/logic/storage.ts`             |

📌 **Toda esta lógica pertenece al dominio “game”**

Estado (`context` + `reducer`)

| Antes                      | Ahora                            |
| -------------------------- | -------------------------------- |
| `context/GameContext.jsx`  | `features/game/GameContext.tsx`  |
| `context/GameProvider.jsx` | `features/game/GameProvider.tsx` |
| `reducer/gameReducer.js`   | `features/game/gameReducer.ts`   |

👉 Context + reducer **son parte del feature**, no infraestructura global.

Estilos

| Antes           | Ahora                |
| --------------- | -------------------- |
| `desktop.css`   | ❌                    |
| `mobile.css`    | ❌                    |
| `tablet.css`    | ❌                    |
| `variables.css` | `styles/globals.css` |

Tailwind reemplaza esto.
Solo dejas:

* reset
* fuentes
* variables globales

---

## Pilares de la arquitectura de software

* Dominio
* UI
* Estado
* Lógica

El dominio define las reglas de negocio; la UI es lo que el usuario ve; El Estado representa los datos actuales de la pantalla; y la Lógica gestiona cómo cambia ese estado basándose en la interacción del usuario.

### Dominio

> **Dominio = las reglas, conceptos y comportamientos del problema que estás resolviendo**

En tu caso:

> 👉 El dominio es **el juego Tic-Tac-Toe**  
> 👉 El dominio es “de qué trata tu programa”
> 👉 Es la explicación de como funciona el juego.

Dominio en una frase

> “Si mañana tuvieras que explicar el juego a alguien SIN mencionar computadoras, eso es el dominio.”

🔥 Dominio aplicado a tu Tic-Tac-Toe

Piensa en el juego en la vida real:

**Tic-Tac-Toe existe aunque no haya computadora**

Tiene:

* jugadores
* turnos
* reglas
* tablero
* ganador o empate

Eso es **dominio puro**.

🔥 Son dominio

* El tablero es 3×3
* Un jugador usa ❌ y el otro ⭕
* Los turnos se alternan
* Hay combinaciones ganadoras
* El juego puede terminar en empate
* Hay modos (PvP, PvC)
* Hay dificultad de la máquina

Nada de eso depende de React.

🔥 NO son dominio

* Un `<button>`
* Un modal
* Tailwind
* JSX
* `useEffect`
* Un `div`

Ejemplos:

```ts
type Board = Array<Player | null>
type GameStatus = 'playing' | 'win' | 'draw'
type GameMode = 'pvp' | 'pvc'
```

📁 `features/game/game.types.ts`

#### Dominio vs UI

❌ UI (cómo se ve)

```tsx
<button className="bg-red-500">
  X
</button>
```

👉 Esto **NO existe fuera de la pantalla**

✅ Dominio (qué significa)

```ts
type Player = 'X' | 'O'
```

👉 Esto existiría aunque el juego fuera en papel.

🧠 Regla mental

> **UI = cómo se muestra**  
> **Dominio = qué significa**

#### Dominio vs Lógica

No son lo mismo, pero están relacionados.

### Lógica

> **Lógica = funciones que aplican reglas del dominio. Gestiona cómo cambia ese estado basándose en la interacción del usuario.**

Ejemplos tuyos:

```ts
checkWinner(board)
getAvailableMoves(board)
makeAIMove(board)
```

Estas funciones:

* no saben de React
* no saben de UI
* solo aplican reglas

📁 `features/game/logic`

#### Analogía rápida

| Concepto | Ejemplo                              |
| -------- | ------------------------------------ |
| Dominio  | “Un tablero tiene 9 casillas”        |
| Lógica   | “Función que revisa si alguien ganó” |

### Estado

> **Estado = la foto actual del dominio en el tiempo**

Ejemplo:

```ts
const state = {
  board: ['X', null, 'O', null, null, null, 'X', null, 'O'],
  currentPlayer: 'X',
  status: 'playing'
}
```

👉 El estado **usa conceptos del dominio**, pero es dinámico.

#### Comparación clave

| Cosa    | Qué es                 |
| ------- | ---------------------- |
| Dominio | Reglas y conceptos     |
| Estado  | Qué está pasando ahora |
| Lógica  | Cómo cambias el estado |
| UI      | Cómo lo ves            |

💥 Esta tabla es oro.

### Dominio explicado con un ejemplo REAL

#### 📌 El juego en papel (dominio)

* Dos jugadores
* Turnos
* Tablero 3×3
* Reglas de victoria

#### 📌 En código (dominio)

```ts
// game.types.ts
export type Player = 'X' | 'O'

export type Cell = Player | null

export type Board = Cell[]

export type GameStatus = 'playing' | 'win' | 'draw'
```

Esto **NO depende de React**.

#### 📌 Lógica (usa el dominio)

```ts
// checkWinner.ts
import { Board } from './game.types'

export function checkWinner(board: Board): Player | null {
  // reglas del juego
}
```

#### 📌 Estado (instancia del dominio)

```ts
const initialState = {
  board: Array(9).fill(null),
  currentPlayer: 'X',
  status: 'playing'
}
```

#### 📌 UI (representación)

```tsx
<Square value={board[index]} />
```

## Analogía final

### 🎲 Juego de mesa

| Mundo real       | Código  |
| ---------------- | ------- |
| Reglas del juego | Dominio |
| Partida en curso | Estado  |
| Árbitro          | Lógica  |
| Tablero físico   | UI      |

## Dónde vive cada cosa en tu estructura

```txt
features/game/
├── game.types.ts     ← DOMINIO
├── logic/            ← LÓGICA
├── gameReducer.ts    ← ESTADO
├── GameContext.tsx   ← ESTADO
├── components/       ← UI
```