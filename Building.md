## Building

Solution will properly load only in Visual Studio 2017 because it contains ASP.NET Core project with .csproj project configuration, which is not supported in 2015. Otherwise there are no other requirements to build from VS, all references should be downloaded from NuGet.

### Build scripts
To build from cmdline run **build.ps1** in PowerShell, script builds Release configuration by default into the same directory.

### Building installer
[Inno Setup](http://jrsoftware.org/isinfo.php) is required to build installer. To build installer run build script with **-Setup** parameter:
``` .\build.ps1 -Installers```

Portable zip package can be built when using **-Portable** parameter.

## Development environment

`Debug` builds are configured to throw exceptions even in cases where `Release` builds would log error message. This is mainly for cases where Playnite can recover and still work properly, but indicates some issue that should be investigated. If you want to suppress these exceptions with `Debug` builds then edit `App.Debug.config` and set `ThrowAllErrors` to `False`.

## Fullscreen mode development
Fullscreen mode uses [custom font files](https://assetstore.unity.com/packages/2d/gui/icons/xbox-one-playstation-4-buttons-pack-77916) that can't be redistributed with Playnite's source. If you want to develop Fullscreen mode you have to obtain your own license or replace them with compatible ones.

## Playnite Services deployment
Several Playnite features are depended on separate Playnite service. Specifically:
* Steam library import
* Steam metadata download
* IGDB integration
* Patreon integration

To deploy your own services instance:
* Navigate to `source\PlayniteServices\` folder
* Create configuration file `customSettings.json`
* Specify content of `customSettings.json` based on `appsettings.json`. For example adding your own Steam API key will look like this:
```
  "Steam": {
    "ApiKey": "customapikeyhere"
  }
```
* You need to provide your own API keys and other values for all empty fields from `appsettings.json` (just for services that you want to use, you can ignore Patreon values for example)
* open cmdline and run `dotnet run` from the same folder
* server should start and listen on port 5000
* **Optional:** Configure root endpoint inside `App.Debug.config` file via `ServicesUrl` key if you start service on other port then default 5000.

**DO NOT run let development builds connect to production service instance. This might potentially lead to serious issues causing problems to all users!**

### Auto-Update
Requires simple web server serving `info.json` file with information about available files. URL with info.json has to be configured in `App.Debug.config` file via `UpdateUrl` key (`http://localhost/update` by default).

Example file:
```
{
    "latestVersion":  "4.21",
    "downloadServers": [
        "http://localhost/build/",
        "http://localhost/mirror/"
    ],
    "releaseNotesUrlRoots" : [ 
        "http://localhost/update/"
    ],
    "packages": [
        {
            "baseVersion" : "4.21",
            "fileName": "421.exe",
            "checksum": "C4CEEA6981242B9087FF9065CE8E5AFD"
        },
        {
            "baseVersion" : "4.2",
            "fileName": "42to421.exe",
            "checksum": "EECEEA6981242B9087FF9065CE8E5AFD"
        },
        {
            "baseVersion" : "4.1",
            "fileName": "41to421.exe",
            "checksum": "BBBEEA6981242B9087FF9065CE8E5AFD"
        }
    ],
    "releaseNotes" : [
        {
            "version" : "4.21",
            "fileName" : "4.21.html"
        },
        {
            "version" : "4.2",
            "fileName" : "4.2.html"
        },
        {
            "version" : "4.1",
            "fileName" : "4.1.html"
        }
    ]
}
```