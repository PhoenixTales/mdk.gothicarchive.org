# ZenGin directory structure

Modding is all about changing the game files and for that we have to know the directory (folder) structure of Gothic.

```
├── Data
│   ├── $Templates$
│   ├── modvdf
│   └── plugins
├── Miles
├── Saves
├── System
│   └── Autorun
└── _work
    └── DATA
        ├── Anims
        │   └── _Compiled
        ├── Meshes
        │   └── _Compiled
        ├── Music
        ├── PRESETS
        ├── Scripts
        │   ├── _compiled
        │   └── content
        │       └── CUTSCENE
        ├── Sound
        ├── Textures
        ├── Video
        └── Worlds
```

## `Data`

The data directory contains [`.vdf` volumes](vdfs/index.md) of the game. These contain `anims.vdf` - animations, `speech.vdf` - dubbing, `worlds.vdf` - world ZEN files.

## `Saves`

Contains saved games.

## `System`

The system directory contains the game executable, `GothicStarter.exe`, `GothicStarter_mod.exe`, configuration `.ini` files, mod `.ini` files, mod icons and description files like `.rtf`.

**`system/Autorun`** is a Union specific directory, it is the default search directory for Daedalus injection scripts with zParserExtender and Union plugins.

## `_work/DATA`

This is where the magic happens:

- `Anims` - animations and animated models.
	- `_compiled` - compiled animations.
- `Meshes` - source meshes and compiled files.
	- `_compiled` - compiled meshes.
- `Music` - music files.
- `Presets` - basic presets.
- `Scripts`
	- `_compiled` - compiled scripts - `.dat` files.
  	- `Content` - scripts that make up the content of the game.
  	- `System` - scripts that make up the menu.
- `Sound` - sound effects in `.wav` format (or `.ogg`, Union only).
- `Video` - videos in the `.bik` format.

