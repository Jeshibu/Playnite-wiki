### Using clean installation

Just unpack beta build and run it. All settings will be stored in the application folder, not affecting any existing installations.

### Using settings and database file from existing installation

#### Standard installation

- Extract beta archive to a custom folder
- Copy content of `%appdata%\Playnite\` into beta folder
- Edit `config.json` and change `DatabasePath` to a new copied library path 

#### Portable installation

- Create copy of existing portable installation
- If you use custom library database location:
  - Make a copy of your [library folder](https://github.com/JosefNemec/Playnite/wiki/Frequently-Asked-Questions#where-can-i-find-library-folder-with-all-games)
  - Edit `config.json` file and set `DatabasePath` to a new copied library path
    - If `DatabasePath` is in `{PlayniteDir}\library` or just `library` format then you don't need to change anything).
- Extract beta archive into copy of portable installation (overwriting all files)
