# LuaG Console - Lua Script - 0.6.1

LuaG uses [lua](https://www.lua.org/) scripts.  
All the scripts must be contained inside the folder `script` (inside `console-userdata`).  
There must be at least a file: `main.lua`.

## main.lua
This is *the main file* of the game.  
It must contain 2 functions:
- `init()` - should be used to initialize variables and load other script files
- `tick()` - is called 60 times per second and should contain ticking and rendering operations

`init()` is called before the game starts, while `tick()` is called while the game is running.

The simplest LuaG program is:  
```lua
function init() end
function tick() end
```

This will do nothing, but the console will run it without problems.

# Console Lua Library

## Variables
| Name   | Description                 |
| ------ | --------------------------- |
| scr_w  | width of screen             |
| scr_h  | height of screen            |
| font_w | width of font's characters  |
| font_h | height of font's characters |
| map_w  | width of game map           |
| map_h  | height of game map          |

## Functions

| Function | Description | Returns |
| --- | --- | --- |
| loadscript(*string* script) | Loads and calls a lua script. The path is relative to `console-userdata/script` | nil |
| key(*int* id) <br> key_down(*int* id) | Checks if a key is down | true or false |
| key_pressed(*int* id) | Checks if a key is pressed | true or false |
| key_released(*int* id) | Checks if a key is released | true or false |
| sfx(*string* sound_name) <br> sfx_play(*string* sound_name) | Plays a sound contained in the 'sfx' folder | nil |
| sfx_loop(*string* sound_name) | Loops the sound until sfx_stop is called | nil |
| sfx_stop(*string* sound_name) | Stops the sound | nil |
| settransparent(*int* color) | Sets the color to be ignored when drawing a sprite | nil |
| clear(*int* color) | Clears the screen | nil |
| pix(*int* x, *int* y, *int* color, *int* width*, *int* height*) | Sets a pixel (or a set of pixels) in the screen | nil |
| write(*string* text, *int* color, *int* x, *int* y) | Draws a text on the screen | nil |
| spr(*int* id, *int* x, *int* y, *int* scale*, *int* spr_width*, *int* spr_height*) | Draws a sprite on the screen. | nil |
| get_tile(*int* x, *int* y) | Returns the id of the tile at x, y | the tile's id (int) |
| set_tile(*int* x, *int* y, *int* id) | Modifies the tile at x, y | nil |
| maprender(*int* scale*, *int* x_offset*, *int* y_offset*) | Renders the map | nil |

*Optional parameter
