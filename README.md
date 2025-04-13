# so_long

This repository contains my implementation of the **so_long** project, developed as part of the 42 School curriculum. The objective of this project is to create a simple 2D game using the MiniLibX library. In this game, the player's goal is to collect all the collectibles on the map and exit through the exit while following the constraints of the game world.

> **Note:** This project is strictly for educational and demonstration purposes. All assets, maps, and textures must respect copyrights.

## Table of Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Common Instructions](#common-instructions)
- [Mandatory Part](#mandatory-part)
  - [Game Requirements](#game-requirements)
  - [Graphic Management](#graphic-management)
  - [Map Requirements](#map-requirements)
- [Bonus Part](#bonus-part)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Error Handling](#error-handling)
- [Submission and Peer Evaluation](#submission-and-peer-evaluation)
- [Acknowledgments](#acknowledgments)
- [Disclaimer](#disclaimer)
- [License](#license)

## Overview

**so_long** is a basic 2D game where the player moves a character on a map, collects all the collectibles, and then exits by choosing the shortest possible route. Although the theme provided in the subject shows a dolphin, fish, and the Earth, you can design your game world and choose your own characters, collectibles, and scenery.

## Objectives

- **Gameplay:** Create a basic computer graphics project using MiniLibX.
- **Window and Event Handling:** Learn to manage windows, process keyboard events, and handle graphical assets.
- **Programming Skills:** Enhance your C programming abilities by following the Norm, managing memory correctly, and applying basic algorithms.
- **Map and Asset Management:** Understand map parsing, validate map design, and integrate external graphic assets.

## Common Instructions

- **Language & Norm:** The project must be written in C and adhere strictly to the Norm.
- **Allowed Functions:** You may use all functions of the MiniLibX, standard C functions (`open`, `close`, `read`, `write`, `malloc`, `free`, etc.), functions from the math library (`-lm`), and your own version of `ft_printf` (or equivalent).
- **Makefile Requirements:** Your Makefile must compile your source files using `-Wall`, `-Wextra`, and `-Werror` with `cc`. It should include the rules `NAME`, `all`, `clean`, `fclean`, and `re`. Bonus rules should be added if applicable.
- **Assets:** You must turn in your map files (with a `.ber` extension), any textures you use, and all required source files.

## Mandatory Part

### Game Requirements

- **Program Name:** `so_long`
- **Goal:** The player's objective is to collect all collectibles and then reach the exit using the shortest route.
- **Controls:**
  - Movement must be controlled with **W, A, S, D** (or alternatively with ZQSD or arrow keys).
  - The game is top-down (or profile view) and non-real-time.
  - The current number of moves should be printed in the shell on every movement.
- **Movement Constraints:** 
  - The player must not be able to move into walls.
  - The game must end when the player exits after collecting all collectibles.
  
### Graphic Management

- **Window:** The game must display its graphics within a window using MiniLibX.
- **Smooth Handling:** Window events (minimization, switching to another window, etc.) must be managed smoothly.
- **Exit Mechanism:** 
  - Pressing the **ESC** key or clicking the window close button must cleanly exit the program.
- **Image Handling:** The use of images with MiniLibX is mandatory to display textures and sprites.

### Map Requirements

- **Input:** The game must take one argument: a map file with a `.ber` extension.
- **Map Characters:**
  - `1` for walls
  - `0` for empty space
  - `C` for collectibles
  - `E` for the exit
  - `P` for the player's starting position
- **Map Validity:**
  - The map must be rectangular and enclosed by walls.
  - There must be exactly one exit, one starting position, and at least one collectible.
  - The map must be parsed to ensure a valid path exists from the player's position to the exit after collecting all collectibles.
- **Error Reporting:** If the map does not meet the criteria (e.g., duplicate exits or starting positions, non-rectangular, not enclosed by walls), the program must exit cleanly and return an error message.

## Bonus Part

For additional bonus points, you can implement one or more of the following features:
- **Enemy Patrol:** Make the player lose when coming into contact with an enemy.
- **Sprite Animation:** Add basic animation to your sprites.
- **On-Screen Movement Count:** Display the number of moves directly on screen, rather than printing them to the shell.
- **Additional Effects or Levels:** Get creative with extra graphical effects or additional gameplay elements.

*Note: Bonus features will only be evaluated if the mandatory part is fully functional and error-free.*

## Project Structure

```
so_long/
├── includes/    # Header files (e.g., so_long.h)
├── srcs/        # Source files for game logic, event handling, and graphic management
├── maps/        # .ber map files used for testing the game
├── textures/    # Image files for textures, sprites, etc.
├── libft/       # (Optional) libft sources and Makefile if used
├── Makefile     # Makefile with required rules: NAME, all, clean, fclean, re (plus bonus if applicable)
└── README.md    # This file
```

## Installation

1. **Clone the Repository:**

   ```sh
   git clone https://github.com/yourusername/so_long.git
   cd so_long
   ```

2. **Build the Project:**

   Use the provided Makefile to compile your source files:

   ```sh
   make
   ```

   This command will produce the executable named `so_long`.

## Usage

Run the game by providing a map file (with a `.ber` extension) as an argument:

```sh
./so_long maps/your_map.ber
```

**Controls:**
- Use W, A, S, D (or your alternative keys) to move.
- The number of moves is printed to the shell after every move.
- To exit the game, press ESC or click the window close button.

## Error Handling

- **Invalid Map File:**
  If the provided map does not comply with the rules (e.g., missing exit, incorrect format, non-rectangular shape, not enclosed by walls), the program must exit cleanly and display an error message ("Error\n" followed by a descriptive message).

- **Memory Management:**
  Ensure that all dynamically allocated memory is freed appropriately to prevent memory leaks.

- **Unexpected Behavior:**
  The program should never crash (i.e., no segmentation faults, bus errors, or double-free issues).

## Submission and Peer Evaluation

- **Submission:**
  Submit your project to the assigned Git repository. Only the files within this repository will be evaluated.

- **Peer Evaluation:**
  During defense, you are allowed to use your own tests and/or those developed by your peers to demonstrate the functionality of your game.

- **File Organization:**
  Make sure that all required files (source files, headers, maps, textures, etc.) are properly named and organized according to the subject guidelines.

## Acknowledgments

- Thanks to the 42 community, mentors, and fellow students for their guidance and support.
- Special thanks to the artists and designers who share free game assets on platforms like itch.io.

## Disclaimer

**IMPORTANT**:
This project was developed solely as part of the educational curriculum at 42 School. The code and assets in this repository are published only for demonstration purposes to showcase my programming and game development skills.

**Academic Integrity Notice**:
It is strictly prohibited to copy or present this code as your own work in any academic submissions at 42 School. Any misuse or uncredited use of this project will be considered a violation of 42 School's academic policies.

## License

This repository is licensed under the Creative Commons - NonCommercial-NoDerivatives (CC BY-NC-ND 4.0) license. You are free to share this repository as long as you:

- Provide appropriate credit.
- Do not use it for commercial purposes.
- Do not modify, transform, or build upon the material.

For further details, please refer to the CC BY-NC-ND 4.0 license documentation.

Developed with passion and in strict adherence to the high standards of 42 School.
