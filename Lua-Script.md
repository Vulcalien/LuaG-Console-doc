# LuaG Console (0.4.0) - Lua Script
LuaG uses [lua](https://www.lua.org/) scripts.<br>
All the script files must be put in the folder [`/console-userdata/script`](Files-and-Folders#console-userdata--folder) and there must be at least one file: `main.lua`.<br>
In your script files, you can use a set of **variables** and **functions** of the console library.

## main.lua
This is *the main file* of the game.<br>
It **must** contain 2 functions:
- `init()` - that should be used to initialize variables and load other script files
- `tick()` - that is called 60 times per second and should contain both ticking and rendering operations

`init()` is called before the game starts, while `tick()` is called while the game is running.

The simplest LuaG '*game*' is:<br>
```lua
function init() end
function tick() end
```

This will do nothing, but the console will run it without problems.

# Console Lua Library

**!** Note that functions' *optional parameters* are indicated using `~`

## Variables
| Name      | Description                 |
| --------- | --------------------------- |
| scr_w     | width of screen             |
| scr_h     | height of screen            |
| font_w    | width of font's characters* |
| font_h    | height of font's characters |
| map_w     | width of game map           |
| map_h     | height of game map          |

*Note that the font is monospaced and letter spacing is 1 pixel.

## General Functions

### loadscript(**script**)
1. `script` ~ string - the path of the script to be loaded

Calls lua's *dofile* for the given script.<br>
The script path is relative to the folder `console-userdata/script`.

returns: `nil`

***

### key(**id**)
1. id ~ int - the id of the key

Keys are set in [`config.json`](Files-and-Folders#configjson--json-file).<br>
`id` represents the index in the keys array.

returns: `true` if the key is pressed, else `false`

***

### sfx(**name**)
1. `name` ~ string - the name of the sound. The '.wav' hasn't to be added

Plays a sound contained in the 'sfx' folder.
Prints an error message if the sound does not exist.

For example this will play '*test.wav*':
```lua
sfx("test")
```

returns: `nil`

## Screen Functions

### settransparent(**color**)
1. `color` ~ int - the color that will be ignored

Sets the color to be ignored when drawing a sprite.<br>
It is useful if you use a background color for sprites.

returns: `nil`

***

### clear(**color**)
1. `color` ~ int - the color that will be used to clear the screen

Clears the screen.

returns: `nil`

***

### pix(**x**, **y**, **color**, ~w, ~h)
1. `x` ~ int - the x of the pixel
2. `y` ~ int - the y of the pixel
3. `color` ~ int - the color of the pixel
4. `w` ~ int ~ (optional, default: `1`) - the number of x-axis pixels
5. `h` ~ int ~ (optional, default: `1`) - the number of y-axis pixels

Sets a pixel (or a set of pixels) in the screen.

returns: `nil`

***

### write(**text**, **color**, **x**, **y**)
1. `text` ~ string - the text to be printed
2. `color` ~ int - the font's color
3. `x` ~ int - indicates the left starting point
4. `y` ~ int - indicates the top starting point

Prints a text on the screen

returns: `nil`

***

### spr(**id**, **x**, **y**, ~scale, ~sw, ~sh)
1. `id` ~ int - the id of the sprite (a number from 0 to 255); the corresponding coordinates are x = id % 16 and y = id / 16
2. `x` ~ int - the x draw coordinate
3. `y` ~ int - the y draw coordinate
4. `scale` ~ int ~ (optional, default: `1`) - the rendering scale of the sprite
5. `sw` ~ int ~ (optional, default: `1`) - the width of the sprite (sw * 8) on atlas
6. `sh` ~ int ~ (optional, default: `1`) - the height of the sprite (sh * 8) on atlas

Draws a sprite in the screen.
The id indicates the position in the atlas (it has 256 sprites, so id can be an integer from 0 to 255)

returns: `nil`

## Map Functions

### gettile(**x**, **y**)
1. `x` ~ int - tile's x
2. `y` ~ int - tile's y

returns: *the tile's id (int)*

***

### settile(**x**, **y**, **id**)
1. `x` ~ int - tile's x
2. `y` ~ int - tile's y
3. `id` ~ int - tile's id

returns: `nil`

***

### maprender(~scale, ~x, ~y)
1. `scale` ~ int ~ (optional, default: `1`) - the render scale
2. `x` ~ int ~ (optional, default: `0`) - the render offset x
3. `y` ~ int ~ (optional, default: `0`) - the render offset y

Renders the map.

returns: `nil`
