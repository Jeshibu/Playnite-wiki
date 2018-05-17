This page describes available settings for emulators and emulator profiles. Every emulator has to have at least on emulator profile.

### Emulator profiles
Profiles provide a way to specify different settings for one emulator. For example you can create 32-bit and 64-bit profiles that would run appropriate version of emulator. Or have `fast` and `accurate` profiles that would run emulator under different configuration (BSNES for example).

### Profile settings

**Supported platforms**
Specifies list of platforms supported by profile. Affects whether the profile will be available when assigning to a game (depending on game's selected platform).

**Executable**
Full path to emulator's executable.

**Arguments**
Emulator's arguments to be used when starting specified executable.

**Working directory**
Startup directory used for specified executable (when empty uses executable's directory).

**Supported File Types**
List of ROM/Image file types supported by emulator profile. Used for game import when scanning folder using specified emulator profile.

### Automatic detection
Playnite can automatically detect various emulators and configure settings for you. Use `Import Emulators` button, select folder containing emulator(s) and Playnite will automatically add detected emulators with predefined profiles.

### Example for snex9x emulator
Executable: `d:\Emulators\SNES\snes9x1541\snes9x.exe`

Arguments: `"{ImagePath}" -fullscreen`

Working Directory: `d:\Emulators\SNES\snes9x1541\`

Supported File Types: `zip, gz, jma, sfc`

### Dynamic variables

Various variables can be used to create dynamic strings. For example when settings emulator arguments `{ImagePath}` variable can be used to pass game's ROM/Image to the arguments.

|Variable|Description|
| ------------- | ------------- |
|{InstallDir}|Game installation directory|
|{InstallDirName}|Name of installation folder
|{ImagePath}|Game ISO/ROM path if set|
|{ImageName}|Game ISO/ROM file name|
|{ImageNameNoExt}|Game ISO/ROM file name without extension|
|{PlayniteDir}|Playnite's installation directory|
|{Name}|Game name
