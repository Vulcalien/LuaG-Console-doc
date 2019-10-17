# LuaG Console - Lua Script - 0.6.0

LuaG uses an integrated shell to make everything: run the game, open the editor, setup blank game files etc...  
The shell works with `commands` and their `arguments`.  
To get a list of the commands, type `help`.

## List of Commands

| Name | Arguments | Description | Developer only |
| --- | --- | --- | --- |
| run | `cartridge's name` or **none** (if dev mode) | Runs a cartridge, or (if no argument) the game being developed | false |
| edit | **none** | Opens the game editor | true |
| pack | `cartridge's name` | Creates a cartridge | true |
| cls | **none** |Clears the shell | false |
| ver | **none** | Prints the console's version | false |
| help | **none** | Prints a list of commands | false |
| mode | `d` (developer) or `u` (user) | Switches console's mode | false |
| files | **none** | Opens `console-userdata` in the file explorer | true |
| setup | **none** | Creates blank game files | true |
| exit | **none** | Shuts down the console | false |
