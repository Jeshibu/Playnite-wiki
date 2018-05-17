ScummVM requires different setup compared to other emulators supported by Playnite. There are multiple ways how to setup ScummVM game, but currently recommended process is:

- Setup your games in ScummVM itself
  - Start ScummVM and use `Add Game` to import your games
- Import ScummVM emulator into Playnite
  - Go to `Tools` -> `Platforms and Emulators` (CTRL-T)
  - Open `Emulators` tab and use `Import Emulators` button to import ScummVM
- Download [ScummVM game import script](https://raw.githubusercontent.com/JosefNemec/Playnite/master/scripts/Extensions/ScummVMImporter.ps1)
  - Save it to [PowerShell scripts folder](https://playnite.link/docs/tutorials/scripting.html#basics)
  - Load the script via `Tools` -> `Reload scripts` (F12)
- Use `Extensions` -> `Import ScummVM Games` menu

All games imported in ScummVM should now show up in Playnite as custom games. You can now use `Download Metadata` from `Tools` menu to fetch covers and additional info for newly added games.