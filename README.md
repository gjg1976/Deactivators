![Alt text](./Deactivators_Coverart.png?raw=true)
# Deactivators
Deactivators, the classic '80 game is back 
This is a game developed with Unreal Engine and shared for free. 
I build this game to learn Unreal Engine and this distribution is to help others in the same way learning from its structure, logic, and source code. It is not a commercial product!

## 📦 Repository Contents

- Game executable
- Unreal Engine game source code.
- Custom assets created by the author (licensed for non-commercial use only).
- 🔴 **Unreal Marketplace assets are not included in the soruce code**: these must be downloaded separately from the Unreal Marketplace as are available for free.


## 🧾 License

The source code in this project is provided for use, study, and modification under the following terms:

> **Allowed for personal, educational, or research use only.**  
> **Commercial or for-profit use is prohibited without the author's explicit permission.**

This includes, but is not limited to:
- Selling the original or modified versions of the game.
- Including any part of the code or assets in paid products.
- Using the project in services that generate direct or indirect revenue.

## Installation and Gameplay
To install the game, simple download the Deactivators_v1.0.0.zip file from link below, unzip and run the deactivators.exe file

https://github.com/gjg1976/Deactivators/releases/tag/v1.0.0

### Playing the Game
The object of the game is to remove all bombs from 5 different buildings You start on level one in a four by four building. The displays at the top of the screen provides a view of waht is going on in two adjacent rooms. At the bottom of the screen is a map of the building showing you the positions of droids and bombs. Each droid is restricted in the number of rooms it can move between. your score is shown in the box on the left, and any bonus droids you have available. The status box on the right shows whether the dorid you are controlling is carrying either a bomb or a circuit board.
To remove the bombs from the building you will have to carry them to the exit and throw them out. There is not always a direct route out of the building, so you will have to throw the bomb between a number of droids to remove it. The exit room is the only room with a dorr which leads to the outside. Certain elements in each building will not function until you replace the corresponding circuit board in the computer room. These include lights, matter transmitters and door or window openings. Some circuit boards are dummies and have no effect and others switch off obstructing forcefields.
You can move around the building in a number of different ways Through the doors, dropping through hatches, sliding up and down poles, or using the matter transporters

### Options
Once the game has loaded, you will see the opening screen. From here you will be able to select either beginner or advance level. On beginner level you will have slower guards, more time and more impacts before the bombs explode.
If you have already played the game but failed, you will be given the opportunity to restart the last level you played with a zero score.
If you manage to remove all bombs from a building, you will placed at the start of the next level.

### Selecting and controlling droid
When an new level starts, or when you press E key,  you will be placed in droid select mode. This is shown by the flashing highlight on the map. By pressing left or right arrow keys, the cursosr can be moved over all the available droids in the building. Presing the E key, take control of selected droid.
To place a bonus droid (if available), select the cursor left or right to highlight the bonus droid and press E key. A simple cursor will now appear over the top left room on the building map. Use arrow keys to position the cursor over the room in which you wish to place the bonus droid and press E. The bonus dorid will appears in the room and you will take control of it.
When in dorid movement mode, use WASD keys to move around.

### Bombs
All the bombs in a building are set to go off in a sequence. If you ara carrying an active bomb you will see the fuse burning in the status display. Be careful when throwing bombs as they can only withstand a limited number of impacts before they will explode. When throwing a bomb through a window or hatch, try and position a droid on the other side to catch it. When the bomb passes into the new room, control will automatically be transferred to the new droid.

### Replacing Circuit Boards
Circuit boards need to be replaced in the computer room to restore the functions of certain elements in the building. there is only one computer room per building. To replace a circuit board, move the droid carrying the circuit board to the back of the computer room until touch the computer, the circuit board will be unload from the droid and installed in the computer. Have fun doing this in the dark on level 4!

### Picking up and throwing objects
A dorid can only carry one object at a time. Trying to pick up a bomb whilst carrying anything else will cause the comb to explode. To pick up either a bomb or a circuit board, move your droid over it. To throw, press the fire key Q to display a trajecmeter showing the angle and direction at which the throw will be made. Move the dorid left, A, or right, D, to select the direction required, and press the Q key to throw when the angle you want to throw at is displayed.
Press the down key and the droid will drop the object carried and return you to movement control mode.
Press the up key and the droid will cancel the throw and retiurn to movement control mode.

### Robot Guards
The robot guards will only chase after an active droid if ther are in the same sector of the building. If you go out of the sector, the freeze and get back to patrol mode. Guards can be destroyed only by making them fall through hatches within a short space of time. If a guard makes contact with an active droid, the droid will disintegrate. If the droid is carrying a bomb, then the bomb will explode

### Scan Mode
In scan mode, moving with arrow keys in any of the four directions will move a cursor over the building map displaying the highlighted rooms. This mode enable you to plan your routes and keep an eye out for any guards which might be lurking in adjacent rooms. Pressing the R key will return you to the location and contorl of the currently active droid. In Building 5, no scan mode is available until one of the circuit boards is replaced in the computer.

### Rooms
Because of the nature of the research being carried out in the building, each room has an individual gravity generator. These have been set to one of four strenghs and the rooms have one of four orientations

### Keyboard Resume
WASD to move the selected droid
Q to open the throwing trajectometer, Q again to throw an object. In this mode use the A or D key to change direction, Down arrow to drop the object and Up arror to cancel
E to change the droid, arrow keys to navigate the available droids, E again to take control od selected droid.
R to view the building, arrow keys to navigate the building, R again to get back to the Deactivator
Backspace to cancel the building game and go to welcome screen, backspace again to get back to main menu
In the welcome screen of each building, press Spacebar to start a building deactivation

## Source Code
The game has been developed using Unreal 5.5.3, with directional gravity plugin, as a learning Unreal Engine taks, this is not intented to be a commercial product or even a free product at all, but a hobby task
A brief description of each class  is included here, please, just download the source code, take a look at it, is easy to understand the code structure

### BP_BuildingGenerator
The game main class, it handles the keyboard input, keep tracking of the rooms assest, update the widget and, of course, creates the building with its rooms.
From the Editor you can define the Map Size and press the InitializeBuilding button to create a Row x Column rooms building, each room is a BP_RoomGenerator class

### BP_Room
Each room in the building is made of a BP_Room, the BP_RoomGenerator creates a Room composed by the lateral walls, the back wall, the ceiling, the floor and the front class. Lateral, back walls and ceiling uses concrete textures, floor use a random marble texture and front wall uses a clear glass texture, but is not render in game.
Each wall is composed of a 4x4 tiles, and border semi tiles, to open hatch, window or door in your building, simple selected the tiles where you whan to open the hole and delete them, be sure to delete the adjacent room too.
Each Room has, also, its own gravity and direction thru the BP_RoomGravity class, from the editor you are able to change the room direction and gravity, changing the gravity will changes the room spot light color too.
You can add assets to a Room, some of these assets are Room ones, meaning you must select the room from the editor, then select the asset and add it, other are asociated to the de tiles, in this case you need to select the tile and added the asset from the editor.
Room assets includes: Deactivator droids, Guardian Droids, Bombs, Circuit Boards, Main Computer, Darkroom
Tile assets includes: Decoration, teleporters and up/down pools
Manually added assets, you need to add it manually from the editor: BP_window (close window), BP_Door (close door), BP_DoorForcefield, BP_ExteriorDoor

### BP_Deactivator3
The main deactivator droid class pawn, it handles all the droid activities (collision, loadouts, enable/disable, etc). You need to add a BP_Deactivator3 for each deactivator in the building, except for player start point which creates a deactivator upon spawn
When a deactivator enables, it will start to make noises

### BP_Guardian
The guardian droid class, it will chase any active deactivator through the sound, its minimal AI uses the BP_NavGridGenerator instead the defualt Unreal Engine one.
The Guardians windstand up to two ground hits before destroyed, both hits shall occurd within least than 20 seconds, otherwise it will autorepair

### BP_Bomb
Each boms uses this class, each one has a start time (for activation) and a blow time, in addition it has the max bouncing counter, the amount of bounces the bomb windstand before blowing

### BP_CircuitBoard
Each computer circuit is of this class, it has the circuit number ID

### BP_Maincomputer
The main computer of each building, it has a number of free slots has circuit boards the building has. Each slot is associated (or not) with one or more trigger interfaces. When a circuit board is inserted into the computer slot (based in the Circuit Board ID), it will trigger the proper interface slot activating/deactivating things
BP_window, BP_door will open, DarkRooms and force fields will be destroyed, teleportes will be enabled

### BP_Teleporter
Each teleporter has a trigger volumen, associated to another teleporter destination, when a Guardian or a Deactivator trigger this volumen will teleporter to destination (if teleporter is enabled), and a destination point used by other teleportes.
It could be disabled, and/or locked. the teleporter exposed the slot_trigger which could be associated to a Main computer slot for enabled it. If a teleporter is locked, the teleportation will happend to its own destination point

### BP_elevator
The up/down pool, when a Guardian or a Deactivator trigger the pool volumen will travel up or down. If the pool is busy it will ignores the target (this is a differece with the original game where a guardian and a deactivator were able to travel at the same time).
A up/down pool could has a force field, which will destroy any deactivator triggering, and it exposed the slot_trigger which could be associated to a Main computer slot for disable the force field

### BP_darkbox
Simple a box painted with a pitch black texture, the box is transparent for objects entering/exiting, but creates the dark room.
It exposed the slot_trigger which could be associated to a Main computer slot for destroing it ("turning the light on")

### BP_ExteriorDoor
A door painted with a pitch black texture, the box will block any deactivator/guardian droid, but let pass the bombs and circuit boards. 
Each bomb triggering the exterior door volumen will be "disabled" . Each board triggering the exterior door will be simple lost
You need to put an exterior door in the buildings, first open a hole in the room tiles and then add, manually, the exterior door

### BP_DoorForcefield
A door's force field, which will destroy any deactivator triggering it. It exposed the slot_trigger which could be associated to a Main computer slot for disable the force field

### Decoration
there are several blueprint with room decorations, these decorations where downloaded from Unreal Markeplace for free and can not be included in this distribution, you need to download for you own from fab

Ceiling light: https://fab.com/s/3d73ce47e633

clock: https://fab.com/s/7534f812496b

Decorative Sconce: https://www.fab.com/listings/9d513596-4c9a-4f12-9e15-729c0d7efb35

Extinguisher: 

Fire Hydrant https://www.fab.com/listings/33bbe5af-77ef-435e-8b8f-f92f692bf91f

LampLED-01: https://fab.com/s/63ee919d4c3f

Yodalarm: https://fab.com/s/4e3292948d33

Frame pop art: https://fab.com/s/0cb10d9489eb

Free wall lamp: https://fab.com/s/efe757decb4b

Industrial pipe: https://fab.com/s/051c5c3d294f

Battle of Actium: https://www.fab.com/listings/64fa03b2-05e4-49c4-b715-453d6e9c481b 

Tiger Hunt: https://www.fab.com/listings/dc7b7120-2359-45dc-89ee-f91fe4b437e5

Young girl in an Apple Orchard: https://fab.com/s/00a6fcf57513

### BP_NavGridGenerator and BP_NavGrid
the default unreal engine AI navigation and chasing system was useless because it only handles "normal" gravity, meaning the nav grid is only available in the "bottom", but for this game whe need the gaurdians chase the deactivators with gravity in any direction, then using the excellent AziApps A-Star tutorial (https://www.youtube.com/playlist?list=PLkppAlnCMgMm0-Ln2fUSBAO3YjSPLSMeh), I build a very rudimentary chasing system
The BP_NavGridGenerator will creates a "depth" BP_NavGrid of row x column size, you need to layout each BP_NavGrid just a little higher than the rooms floor, wherever the floor is pointing up/down/right/left. Delete any grid tile within a wall. You can add additional ExtraCost to avoid the guardian step on it, unless no other option, as example to avoid hatches it are in the direct route, you can mark any grid as not walkable
From the BP_NavGridGenerator you are able to create "links" between the BP_NavGrid, which allows the Guardians to chase you through teleportes and hatches.
Sadly I have no time to make the thing more automatic, then you need to do averithing manually, the layout ot the navgrid in the rooms, the links between grids through teleportes and hatches, the avoidance of not optimal paths, etc, etc. It is a work to do for get a better chasing system, but it is usefull as is

### Widgets
The game have a main widget which will show the main interface with the building minimap with the deactivators and bombs position, the score, bonus droids, droid loadout and the two main cameras showing a room each one. I use a Real Time render teture to do the dual camera vision
Another widget is the main menu and the entering name menu



