# LuaG Console (0.4.0) - Files and Folders

There are some files that the user must have to make the console work.

## console-userdata | (folder)
This is the root folder for your game, and is located in *the same folder of the console .jar file*.<br>
This folder contains a set of files and folders, that are necessary to make the console run without problems.<br>
*All the files of your project are **inside** `console-userdata` and all the folders are **subfolders** of it*.
### A list of these files
| File          | Type          |
| ------------- | ------------- |
| `script`      | folder        |
| `sfx`         | folder        |
| `config.json` | json file     |
| `atlas.png`   | 128x128 image |
| `map`         | binary file   |

## script | (folder)
This is the folder where you will put all your code files.<br>
You can also use subfolders to better organize your game files.<br>

The only file there **must** be is `main.lua`, that will be automatically called on console startup.

## sfx | (folder)
This folder contains your game sounds. *Sound files must be **'.wav' files***.<br>
`sfx` **cannot** contain subfolders at the moment.

## config.json | (json file)
This file contains user informations.<br>
It must contain a string array, 'keys'.<br>
Example:
```json
{
    "keys": [
        "W", "A", "S", "D"
    ]
}
```

The order of the keys gives them an **id**. In this case, [`key(1)`](Lua-Script#keyid) will refer to the key *A*.

## atlas.png | (128x128 image)
This png file is used as *sprite atlas* by the console.<br>
Each sprite is 8x8 pixels, so the entire atlas contains **256 sprites**.<br>
The position of a sprite gives it an `id` (0 to 255).

## map | (binary file)
This file is used by the console and **should not be modified manually**.<br>
Instead, use the **integrated map editor**.
