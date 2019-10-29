# Unity Tetris Inventory System in C#

# Description
This project is composed of C# files, that were programmed in visual studio linked to Unity 2019.2.4f1 (64bits).

The main ideia of this project is to implement a Tetris Inventory in Unity. The tetris inventory is the same used in Resident Evil 4 and Diablo. Unfortunately I did not find any good stuff in the internet, so I developed it by my own (which means that it could be optimized yet).

I used this files in a 2D roguelike indie game [unfinished]. The project that will be provided just have a simple player movement and camera follow script, and the inventory tetris with item decription.

![Tetris Inventory](/images/TetrisInventory.png)


To use this files, you will need to make some tailoring in the code, to fit your own way on collecting/dropping items.


# Keys
* **Player Movement**: A W S D
* **Inventory**: I
* **PickUp Item**: K
* **Drag / Drop / Use / Description**: Mouse

To drop an item, drag it over the wood box.

# Functionalities
* **PickUp** item on the floor and **Add** in the inventory.
* **Remove** item from the inventory and **Drop** it on the floor.
* **Drag** items in the inventory and **Check** if the item fits.
* **Display** item description when pointing mouse over it.
* **Rescale** item based on it (X, Y) size.

# Getting Started
There are a few folders in the game, being them:

* Fonts -> personalized font to show item description
* Prefabs -> empty slot prefab (SlotTetris), item prefabs, prefab of the items that will go to inventoy (itemSlotTetris).
* Scenes -> just have one.
* ScriptableItems -> two scriptable Items with different sizes that can be collected by the player, and have its own characteristics.
* Scripts -> Have the Player Scripts, Tetris Inventory Scripts (inside of it, there is the itensToUse, which is the scripts for the items that when clicked in the inventory can be used and perform some action in the gameWorld, in this case, it is a potion), Camera Follow Script and, the script to turn items collectables.
* Tileset -> All tiles used in the scene and some more.


# Scripts
* Collectable
  * Responsible for picking up items from the floor.
 
* cameraFollow
  * Follow the player.
 
* Functionalities
  * Change item description on canvas and enable openning inventory pressing the key: I.

**Tetris Inventory Scripts**

* TetrisInventory
  * Put this script in the player or game manager that will not be destroyed during the game. This file is just to set how many slots will be spawned.
  
* TetrisItem
  * (ScriptableObject), creates new asset menu in Inventory/Tetris/Item. It is the base script for creating Items and its derivatives.

* TetrisListItens
  * Contains all items prefabs that will be available in the game. Used to drop the item without having it prefab instantiated.
  

Now the most important files:

* TetrisItemSlot (Most Important)
  * Responsible for each slot that contains the item (item slot by itself), contains the drag actions, rescale slot size based on itemSize (X, Y), drop items.
   * Be sure to change the size parameter to your own cell size.
   
* TetrisSlot (Most Important)
  * Responsible for the invisible Tetris grid, controls where have an item, free spaces, undesired positions, and others.
  * The cellSize parameter must be the same used in the size parameter in the TetrisItemSlot script.
  * maxGridX parameter is the number of slots in the horizontal line. (In my case I used 14).
  
* TetrisUI
  * Responsible for creating the background grid that will be behind the collected items, creates the number of cells that were set in the TetrisInventory script.
  
  # Observations
* The code was first wrote in portuguese, so I apologize if I forgot to change some parts to english, or if there is grammar mistakes.
* The Sprite Art was not made for me, please change to yours! Use this just to study.
* Feel free to use this code and change however you want. If there is some doubt remaining let me know.
* Hope this helps.
* Follow me on LinkedIn: https://www.linkedin.com/in/bryangalani/
