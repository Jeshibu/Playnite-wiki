### Using clean installation

Just unpack beta build and run it. All settings will be stored in the application folder, not affecting any existing installations.

### Using settings and database file from existing installation

#### Existing standard installation

- Extract beta archive to a custom folder
- Copy content of `%appdata%\Playnite\` into beta folder
- If you use custom database location:
  - Make a copy of your database file
  - Edit `config.json` file and set `DatabasePath` to a location of your copied file

#### Existing portable installation

- Create copy of existing portable installation
- If you use custom database location:
  - Make a copy of your database file
  - Edit `config.json` file and set `DatabasePath` to a location of your copied file
- Extract beta archive into copy of portable installation (overwriting all files)
