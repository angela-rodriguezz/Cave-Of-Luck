# Cave-Of-Luck

![](https://github.com/angela-rodriguezz/Cave-Of-Luck/blob/main/game%20gif.gif)

A procedural world generation game in which you enter an integer as a seed and receive a new combination of rooms and hallways to explore! Each time the world is generated, the player gets new orb locations which foretell a lucky combination of lottery numbers that you can play for your town's next lottery. Play and gain a higher chance of winning this year's lottery!

Executed the world generation algorithm, UI, main menu interface, saving/loading, and user interactivity game mechanics.

## Video Demonstration
[Click Here!](https://www.youtube.com/watch?v=FtFxGPzvim0)

## Development Process

### Part 1: Room Generation Algorithm

![RoomImage](https://sp23.datastructur.es/materials/proj/proj3/img/compliant_world_example.png)

I used Java's ``Tileset`` and ``StdDraw library`` to implement the room generation algorithm.

In order to generate the output of rooms in the Tile system, I implemented an algorithm similar to Dijkstra's algorithm. For instance, first generating random coordinates within the 2D grid interface and then building the the rooms across the grid separately at first. Each room is generated in a rectangular shape and pseudo-randomly generated. 

After randomly generating rooms based on different seeds the player inserts in the main menu [(discussed later here!)](#part-3:-heads-up-display-creation), we must connect each room together by a hall. Since the locations of the rooms and hallways should be random, each of the hallways should be built from the 

### Part 2: Main Menu System

![Menu](https://github.com/angela-rodriguezz/Cave-Of-Luck/blob/6d05b5eb8dadd476c616334184b7eb74c11c71e6/cavemenu.png)

With this system, we need to first handle the generation of a new game that prompts the user to enter a “random seed” of any long value of their choosing. Luckily, the `Core.Engine` system that is integrated within the project contains the `interactWithInputString()` and `interactWithKeyboard()` which identifies the user output and what character is outputted from the user. When a user types `N`, a pop up window appears to await user input of any number that aides in the room generation process.

### Part 3: Heads-Up Display Creation

![HUD](https://sp23.datastructur.es/materials/proj/proj3/img/UI_example0.png)

