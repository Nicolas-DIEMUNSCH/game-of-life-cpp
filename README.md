# Game of Life — C++ OOP Simulation

> An object-oriented implementation of Conway's Game of Life in standard C++, with console and SFML graphical modes.

## Overview

This project implements John Conway's Game of Life using an object-oriented approach in C++. It separates the game engine, grid management, cell states, rules, file handling, and graphical rendering into distinct classes.

The program reads an initial grid from a text file, evolves the simulation according to Conway's rules, and can run either in console mode or in a graphical SFML window.

## Features

- Conway's Game of Life rules.
- Object-oriented architecture with polymorphism.
- Normal and toric grid implementations.
- Console mode that exports successive generations to output files.
- SFML graphical mode.
- Support for obstacle cells.
- Unit tests for validating grid evolution.
- Predefined patterns such as glider, cannon, and larger structures.

## Tech Stack

| Component | Technology |
|---|---|
| Language | C++ |
| Standard Library | STL |
| Graphics | SFML |
| Design | OOP, SOLID principles |
| Testing | Unit tests |

## Project Structure

```text
project-root/
├── main.cpp
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
├── test.cpp
├── *.txt
└── README.md
```

## How It Works

1. The program receives the path to an input file.
2. The file provides the grid dimensions and the initial state.
3. The game engine builds the objects needed for the simulation.
4. Each generation updates the grid according to the selected rules.
5. The simulation stops when the system stabilizes or when the maximum number of iterations is reached.

## Input File Format

The input file starts with the grid dimensions, followed by a matrix of booleans:

```text
5 10
0 0 1 0 0 0 0 0 0 0
0 0 0 1 0 0 0 0 0 0
0 1 1 1 0 0 0 0 0 0
0 0 0 0 0 0 0 0 0 0
0 0 0 0 0 0 0 0 0 0
```

- `1` = alive cell.
- `0` = dead cell.

## Available Modes

### Console mode

The program writes the first generations to output files using the expected format.

### Graphical mode

The simulation runs in an SFML window and displays the current state of the grid in real time.

## Extensions

- Toric grid handling.
- Obstacle cells.
- Built-in patterns placed from text files.
- Unit tests for simulation correctness.

## Setup

### Requirements

- C++ compiler
- SFML
- CMake or a compiler toolchain of your choice

### Build and run

```bash
# Example only
mkdir build
cd build
cmake ..
cmake --build .
./game_of_life
```

## Tests

The project includes unit tests to verify the evolution of the grid after a chosen number of iterations.

## Team

- Nicolas Diemunsch
- Pierre Lambert

## License

Academic project.
