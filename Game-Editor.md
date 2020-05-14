# LuaG Console - Game Editor - 0.6.2

To develop a game in LuaG Console, you can use an integrated editor. It consists of a `map editor` and a `sprite editor`. To open it, you have to be in [dev mode](https://github.com/Vulcalien/LuaG-Console/wiki/Dev-Mode) and use the command `edit`.

The editor has a menu with buttons used for moving from one editor to another. The first of them closes the editor and opens the shell (remember to save before doing this!).  
The button in the right saves the game files.

**IMPORTANT**: switching from an editor to another will not cancel the edits, but the go-to-shell button will.

## Map Editor
![Image of the map editor](https://raw.githubusercontent.com/Vulcalien/LuaG-Console/documentation/images/map-editor.png)

The map editor is composed of 3 components:
- editing area
- map's size panel
- sprite atlas

In the editing area, you can move the map using `WASD` keys and setting a tile using `left click`.  
The map's size panel is used to modify the map size (press `ENTER` to modify it).  
The sprite atlas is used to select the tile you want to set. It can be scrolled up and down using `mouse wheel`.

## Sprite Editor
![Image of the sprite editor](https://raw.githubusercontent.com/Vulcalien/LuaG-Console/documentation/images/sprite-editor.png)

The sprite editor is used to create and edit game sprites.  
It has a toolbar in the left with 5 tools:
- pencil
- fill bucket
- color picker
- undo
- redo

The editing area is in the center and you can use tools on it using `left click`.  
The right panel is used to choose the color you want to use.  
The sprite atlas in the bottom, like the one in Map Editor, is used to select the tile. Switching from a tile to another will **not** cancel the edits on the previous tile.
