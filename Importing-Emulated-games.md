Playnite can start emulated games though any emulator that supports running specific game images via cmdline arguments.

To properly import emulated game:
1. Setup an emulator via `Library -> Configure Emulators` menu.
- Playnite can automatically import [several well known](https://github.com/JosefNemec/Playnite/blob/master/source/Playnite/Emulators/Definitions.yaml) emulators and will set all emulator properties for you. To import an emulator use `Import Emulators` button.
- If you want to use unsupported emulator or configure it by yourself then see [[Adding new emulator]] page for more details about emulator properties.
2. Import game image (ROM) via `Add Game -> Emulated Game` menu.
- You need to select emulator and its profile to scan the image files with.

### Troubleshooting
If you are getting an error while starting emulated game saying something like "system cannot find the file specified", that means that emulator configuration doesn't point properly to emulator executable. Make sure that valid executable name and path is set for used emulator via `Library -> Configure Emulators`.