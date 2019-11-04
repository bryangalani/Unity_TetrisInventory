# Unity Tetris Inventory System in C#

# Description
The Unity project is packed in .rar file and is composed of C# files, that were programmed in visual studio linked to Unity 2019.2.4f1 (64bits). Just unpack the file to import the project in Unity.

The main idea of this project is to implement a Tetris Inventory in  Unity. The Tetris inventory is the same used in Resident Evil 4 and  Diablo. Unfortunately, I did not find any good stuff on the internet, so I  developed it on my own (which means that it could be optimized yet).

I used these files in a 2D roguelike indie game [unfinished]. The project that will be provided just have a simple player movement and a camera follow script, and the inventory tetris with item description.

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
* **Display** item description when pointing the mouse over it.
* **Rescale** item based on it's (X, Y) size.

# Getting Started
There are a few folders in the game, being them:

* Fonts -> personalized font to show item description
* Prefabs -> empty slot prefab (SlotTetris), item prefabs, prefab of the items that will go to inventory (itemSlotTetris).
* Scenes -> just have one.
* ScriptableItems -> two scriptable Items with different sizes that can be collected by the player, and have its characteristics.
* Scripts -> Have the Player Scripts, Tetris Inventory Scripts (inside of it, there is the itensToUse, which is the scripts for the items that when clicked in the inventory can be used and perform some action in the gameWorld, in this case, it is a potion), Camera Follow Script and, the script to turn items collectables.
* Tileset -> All tiles used in the scene and some more.


# Scripts
* Collectable
  * Responsible for picking up items from the floor.
 
* cameraFollow
  * Follow the player.
 
* Functionalities
  * Change item description on canvas and enable opening inventory pressing the key: I.

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
   * Be sure to change the size parameter to your cell size.
   
* TetrisSlot (Most Important)
  * Responsible for the invisible Tetris grid, controls where have an item, free spaces, undesired positions, and others.
  * The cellSize parameter must be the same used in the size parameter in the TetrisItemSlot script.
  * maxGridX parameter is the number of slots in the horizontal line. (In my case I used 14).
  
* TetrisUI
  * Responsible for creating the background grid that will be behind the collected items, creates the number of cells that were set in the TetrisInventory script.
  
  # Observations
* The code was first written in Portuguese, so I apologize if I forgot to change some parts to English, or if there are grammar mistakes.
* **The Sprite Art was not made for me, please change to yours! I cut off most of them from the project. Use the remaining sprites just to study.**
* Feel free to use this code and change however you want. If there is some doubt remaining let me know.
* Hope this helps.
* Follow me on LinkedIn: https://www.linkedin.com/in/bryangalani/

# License
MIT License

Copyright (c) 2019 Bryan Stefan Galani Pernambuco

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
