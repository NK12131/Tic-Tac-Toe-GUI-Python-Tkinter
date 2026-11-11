# ❌⭕ Tic-Tac-Toe GUI

> A two-player Tic-Tac-Toe desktop game built with Python and Tkinter. Players enter their names on a welcome screen and take turns on a 3×3 board. A pop-up announces the winner or a tie.

---

## ✨ Features

- **Welcome screen** where Player 1 (X) and Player 2 (O) enter their names
- **Name check**: the game won't start until both names are filled in
- **3×3 board** of clickable buttons, with X and O placed in alternating turns
- **No overwriting**: a square that's already taken can't be clicked again
- **Win detection** across all 8 lines (3 rows, 3 columns and 2 diagonals)
- **Winner pop-up** that shows the winning player's name
- **Tie pop-up** when the board fills with no winner, returning to the welcome screen for a rematch
- **NEXT** and **EXIT** buttons on the welcome screen

---

## 🧰 Tech Stack

| Component | Technology |
|-----------|------------|
| Language  | Python 3 |
| GUI       | Tkinter (`Tk`, `Label`, `Entry`, `Button`, `messagebox`) |
| Layout    | Tkinter `grid` geometry manager |

There are no third-party dependencies. Tkinter comes with the standard Python installer.

---

## 📁 Project Structure

```
Tic-tac-toe_GUI/
├── TICTACTOEGUI_final_hopefully.py   # The full game: welcome screen + board
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
- **Python 3.x** with Tkinter
  - **Windows / macOS:** included with the installer from [python.org](https://www.python.org/downloads/)
  - **Linux (Debian/Ubuntu):** `sudo apt install python3-tk`

Check that Tkinter is installed:
```bash
python3 -m tkinter
```
This should open a small test window.

### Run the game
```bash
git clone https://github.com/<your-username>/Tic-tac-toe_GUI.git
cd Tic-tac-toe_GUI
python3 TICTACTOEGUI_final_hopefully.py
```

---

## 🎮 How to Play

1. Enter a name for **Player 1 (X)** and **Player 2 (O)**, then click **NEXT**.
2. Players take turns clicking an empty square. **X always goes first.**
3. The first player to get three marks in a row (horizontally, vertically or diagonally) wins.
4. If all nine squares are filled and nobody has three in a row, the game is a tie.
5. Click **EXIT** on the welcome screen to quit.

> **Note:** The window's close (✕) button is disabled on the welcome screen, so use **EXIT** to quit.

---

## ⚙️ How It Works

| Function | Role |
|----------|------|
| `next()` | Checks that both names are entered, then opens the game window and builds the 3×3 board |
| `clicked1()` … `clicked9()` | Handle clicks on each square: place X or O, switch turns, then call `check()` |
| `check()` | Reads the board after every move, tests all 8 winning lines, and counts moves to detect a tie |
| `win(player)` | Shows a pop-up with the winner's name and closes the game |
| `exitplease()` | Closes the application |

---

## 🐞 Known Issues

- If the 9th move wins the game, the tie check still runs after the winner pop-up closes the window, which can raise a Tkinter error.
- On macOS, the black button background may not appear, because native buttons ignore `bg`.
- The game window is created with a second `Tk()` instance. A `Toplevel()` window is the standard Tkinter approach.

## 🛣️ Possible Improvements

- [ ] Replace the nine `clicked` functions with one function that takes the square's position
- [ ] Store the board in a list and loop over a table of winning lines
- [ ] Add a **Play Again** button and a running scoreboard
- [ ] Highlight the winning line
- [ ] Add a single-player mode against the computer (for example, using minimax)
- [ ] Rename the script to something cleaner, such as `tictactoe.py`