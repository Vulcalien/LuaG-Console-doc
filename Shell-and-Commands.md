# LuaG Console - Shell and Commands - 0.6.2

LuaG uses an integrated shell to make everything: run the game, open the editor, setup blank game files etc...  
The shell works with `commands` and their `arguments`.  
To get a list of the commands, type `help`.

## List of Commands

| Name | Arguments | Description | Developer only |
| --- | --- | --- | --- |
| run | `cartridge's name` or **none** (if dev mode) | Runs a cartridge, or (if no argument) the game being developed |
| edit | **none** | Opens the game editor | Yes |
| pack | `cartridge's name` | Creates a cartridge | Yes |
| cls | **none** | Clears the shell |
| ver | **none** | Prints the console's version |
| help | **none** | Prints a list of commands |
| mode | `d` (developer) or `u` (user) | Switches console's mode |
| files | **none** | Opens `console-userdata` in the file explorer | Yes |
| setup | **none** | Creates blank game files | Yes |
| exit | **none** | Shuts down the console |
