# LuaG Console - lua Script - 0.6.3

LuaG uses [*lua*](https://www.lua.org/) 5.2 scripts. Those scripts have to be put inside the folder `script` (inside `console-userdata`).\
The main file is `main.lua` but it's possible to use multiple files.

## main.lua
This is *the main file* of the game.\
It must contain 2 functions:
- `init()` - called once, should be used to initialize variables and load other script files
- `tick()` - called 60 times per second, should contain ticking and rendering operations

`init()` is called before the game starts, while `tick()` is called while the game is running.

The simplest LuaG program is:\
```lua
function init() end
function tick() end
```

This will do nothing, but the console will run it without problems.

## lua environment
The lua interpreter **does not load** all the default libraries. Only libraries that are necessary for games are loaded.

Loaded: Base, Package, Bit32, Math, Table, String, LuaG Interface.\
Not Loaded: Coroutine, Io, Os, Lua-Java.\
Also, `require` is disabled (you can use `loadscript` instead).

When there is an error, it's logged in the *log file*, that can be opened using the `log` command when in [dev mode](https://github.com/Vulcalien/LuaG-Console/wiki/Dev-Mode).

## Game interface

### Variables

| Name   | Description                 |
| ------ | --------------------------- |
| scr_w  | width of screen             |
| scr_h  | height of screen            |
| font_w | width of font's characters  |
| font_h | height of font's characters |
| map_w  | width of game map           |
| map_h  | height of game map          |

### Functions

| Function                                                               | Description                                                                 |     Returns     |
| ---------------------------------------------------------------------- | --------------------------------------------------------------------------- | :-------------: |
| loadscript(string script)                                              | Loads and calls a lua script. Path is relative to `console-userdata/script` |       nil       |
| log(string x)                                                          | Prints something in the log file                                            |       nil       |
| key(int id) <br> key_down(int id)                                      | Checks if a key is down                                                     |  true or false  |
| key_pressed(int id)                                                    | Checks if a key is pressed                                                  |  true or false  |
| key_released(int id)                                                   | Checks if a key is released                                                 |  true or false  |
| sfx(string sound_name) <br> sfx_play(string sound_name)                | Plays a sound contained in the 'sfx' folder                                 |       nil       |
| sfx_loop(string sound_name)                                            | Loops the sound until sfx_stop is called                                    |       nil       |
| sfx_stop(string sound_name)                                            | Stops the sound                                                             |       nil       |
| settransparent(int color)                                              | Sets the color to be ignored when drawing a sprite                          |       nil       |
| clear(int color)                                                       | Clears the screen                                                           |       nil       |
| pix(int x, int y, int color, int width*, int height*)                  | Sets a pixel (or a set of pixels) in the screen                             |       nil       |
| write(string text, int color, int x, int y)                            | Draws a text on the screen                                                  |       nil       |
| spr(int id, int x, int y, int scale*, int spr_width*, int spr_height*) | Draws a sprite on the screen.                                               |       nil       |
| get_tile(int x, int y)                                                 | Returns the id of the tile at (x, y)                                        | tile's id (int) |
| set_tile(int x, int y, int id)                                         | Modifies the tile at (x, y)                                                 |       nil       |
| maprender(int scale*, int x_offset*, int y_offset*)                    | Renders the map                                                             |       nil       |

*Optional parameter
