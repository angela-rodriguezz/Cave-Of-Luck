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

After randomly generating rooms based on different seeds the player inserts in the main menu [(discussed later here!)](#part-3-heads-up-display-hud-creation), we must connect each room together by a hall. Since the locations of the rooms and hallways should be random, each of the hallways should be built starting from the random point we generated earlier for the room. From there, we create a path from this point to the closest possible room that we generated using a hashmap to record all room point locations on the grid.

Lastly, each hallway and room is bordered by walls. We do this by adding a tile above or below the hall tiles that we have created in the grid previously.

### Part 2: Main Menu System

![Menu](https://github.com/angela-rodriguezz/Cave-Of-Luck/blob/6d05b5eb8dadd476c616334184b7eb74c11c71e6/cavemenu.png)

With this system, we need to first handle the generation of a new game that prompts the user to enter a “random seed” of any long value of their choosing. Luckily, the `Core.Engine` system that is integrated within the project contains the `interactWithInputString()` and `interactWithKeyboard()` which identifies the user output and what character is outputted from the user. 

- Typing `N` reveals a pop up window to await user input of any number that enables the room generation process.
- Typing `L` loads your progress in the game of which you had started playing previously.
- Typing `I` reveals the pop up window for the background and directions of the game.
- Typing `E` allows you to choose the name of the character that will be moving across the map. This name will appear within the HUD when the game begins.
- Typing `Q` quits the application.

### Part 3: Heads-Up Display (HUD) Creation

![HUD](https://sp23.datastructur.es/materials/proj/proj3/img/UI_example0.png)

Now, instead of measuring keyboard input, we must measure mouse hover input. Using the StdDraw library, we have the mouseX and mouseY component which examines if the mouse hovers over any area of the map. If the mouse hovers a new area that is not the same component as the one previously, the HUD will change the description on the top left corner of the screen to match the new component.

Furthermore, the score is marked to illustrate if the player has collected any items. If so, the score changes from 0 to the lucky number that was generated within the item. Also any name that the user typed within the main menu is always displayed on the top right corner of the screen.

### Part 4: Saving & Loading

In order to regenerate the world after quitting, we must recover the list of moves and keyboard commands the user had used previously. We can record these moves within a saved document, registering them until the next load. Therefore, the world is generated the same way that it was before quitting.



