# 🎮 Conway's Game of Life — C++ Simulation

C++ project built as part of a POO assignment.

This project implements Conway's Game of Life using a clean object-oriented architecture. The application reads an initial grid from a text file, evolves the simulation generation after generation, and can run both in console mode and in graphical mode with SFML.

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Running the Project](#-running-the-project)
- [Tests](#-tests)
- [Team](#-team)

---

## 🌐 Project Overview

Conway's Game of Life is a cellular automaton where each cell is either alive or dead. Its next state depends on the number of live neighbors around it.

This project was designed to respect object-oriented programming principles as much as possible. The game, the grid, the rules, and the cell states are all handled by dedicated classes, and the graphical interface is separated from the simulation logic.

| Mode | Description |
|------|-------------|
| Console | Exports successive generations to output files |
| Graphical | Displays the simulation in an SFML window |

---

## ✨ Features

### Core simulation
- Conway's original evolution rules.
- Object-oriented design with polymorphism.
- Grid and game logic separated into reusable classes.
- File input for the initial configuration.
- Automatic stop when the simulation stabilizes.

### Grid management
- Normal grid mode.
- Toric grid mode.
- Support for obstacle cells.
- Grid factory to create the correct grid type.

### Input and output
- Reads the initial state from a text file.
- Writes successive generations in console mode.
- Uses predefined pattern files such as glider, cannon, and larger patterns.

### Graphical mode
- SFML-based interface.
- Visual rendering of the cell grid.
- Clean separation between GUI and simulation logic.

### General
- Unit tests for validation.
- Standard C++ with STL.
- Designed to be efficient and extensible.

---

## 🛠 Tech Stack

| Component | Technology |
|-----------|------------|
| Language | C++ |
| Standard Library | STL |
| Graphics | SFML |
| Design | OOP, polymorphism, SOLID principles |
| Testing | Unit tests |
| Input format | Plain text `.txt` files |

---

## 🏗 Architecture

The project is organized around a clear separation of responsibilities:

```text
project-root/
├── main.cpp
├── test.cpp
├── Game.h / Game.cpp
├── Grid.h
├── GridNormal.h / GridNormal.cpp
├── GridToric.h / GridToric.cpp
├── GridFactory.h / GridFactory.cpp
├── CellState.h
├── CellAlive.h / CellAlive.cpp
├── CellDead.h / CellDead.cpp
├── Rules.h
├── ConwayRules.h / ConwayRules.cpp
├── FileManager.h / FileManager.cpp
├── AffichageGraphique.h / AffichageGraphique.cpp
├── *.txt
└── README.md
```

### Main responsibilities

| Module | Role |
|--------|------|
| `Game` | Manages the simulation and generations |
| `Grid` | Defines the grid interface |
| `GridNormal` / `GridToric` | Concrete grid implementations |
| `CellState` | Base class for cell states |
| `CellAlive` / `CellDead` | Alive and dead cell behaviors |
| `Rules` / `ConwayRules` | Encapsulate evolution rules |
| `FileManager` | Loads and saves grid states |
| `AffichageGraphique` | Handles the SFML rendering |

---

## ⚙️ Installation

### Prerequisites

- C++ compiler
- SFML library
- CMake or a compatible build tool

### Steps

**1. Clone the repository**
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

**2. Build the project**
```bash
mkdir build
cd build
cmake ..
cmake --build .
```

**3. Run the executable**
```bash
./game_of_life
```

---

## 🔧 Configuration

The program expects an input `.txt` file containing the initial grid state.

### Input format

```text
5 10
0 0 1 0 0 0 0 0 0 0
0 0 0 1 0 0 0 0 0 0
0 1 1 1 0 0 0 0 0 0
0 0 0 0 0 0 0 0 0 0
0 0 0 0 0 0 0 0 0 0
```

- First line: grid dimensions.
- Following lines: cell matrix.
- `1` means alive.
- `0` means dead.

---

## 🚀 Running the Project

### Console mode

Launch the program with the input file path. The simulation writes the next generations into output files inside a dedicated output folder.

### Graphical mode

Launch the program in graphical mode to open the SFML window and display the evolving grid.

---

## 🧪 Tests

Unit tests are provided to verify the evolution of the grid after a chosen number of iterations.

```bash
./tests
```

---

## 👥 Team

Built by a team of 2.

| Name | Role |
|------|------|
| To be filled | To be filled |
| To be filled | To be filled |

---

## 📄 License

Academic project — all rights reserved.
