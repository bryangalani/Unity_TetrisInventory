# Unity Tetris Inventory C#
C# Unity Projects 2019/2020

# Description
This project is composed of C# files, that were programmed in visual studio linked to Unity 2019.2.4f1 (64bits).

The main ideia of this project is to implement a Tetris Inventory in Unity. The tetris inventory is the same used in Resident Evil 4 and Diablo. Unfortunately I did not find any good stuff in the internet, so I developed it by my own (which means that it could be optimized yet).

I used this files in a 2D roguelike indie game [unfinished].

![Tetris Inventory](/images/TetrisInventory.png)


To use this files, you will need to make some tailoring in the code, to fit your own way on collecting/dropping items.
The code is commented.

# Scripts

* TetrisInventory
  * Put this script in the player or game manager that will not be destroyed during the game. This file is just to set how many slots will be spawned.
  
* TetrisItem
  * (ScriptableObject), creates new asset menu in Inventory/Tetris/Item. It is the base script for creating Items and its derivatives.

* TetrisListItens
  * Contains all items prefabs that will be disponible in the game. Used to drop the item without having it prefab instantiated.

Now the most important files:

* TetrisItemSlot (Most Important)
  * Responsible for each slots that contains the item (item slot by itself), contain the drag actions, reescale slot size based on itemSize (X,Y), drop items.
   * Be sure to change the size parameter to your own cell size.
   
* TetrisSlot (Most Important)
  * Responsible for the invisible Tetris grid, controls where have an item, free spaces, undesired positions and others.
  * The cellSize parameter must be the same used in the size parameter in the TetrisItemSlot script.
  * maxGridX parameter is the number of slots in the horizontal line. (In my case I used 14).
  
* TetrisUI
  * Responsible for creating the background grid that will be behind the collected itens, creates the number of cells that were set in the TetrisInventory script.
