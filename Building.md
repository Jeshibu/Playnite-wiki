## Building

Solution will properly load only in Visual Studio 2017 because it contains ASP.NET Core project with .csproj project configuration, which is not supported in 2015. Otherwise there are no other requirements to build from VS, all references should be downloaded from NuGet.

### Build scripts
To build from cmdline run **build.ps1** in PowerShell, script builds Release configuration by default into the same directory. Script accepts *Configuration*, *OutputPath*, *Setup*, *Portable* and *SkipBuild* parameters.

### Building installer
[NSIS 3+](http://nsis.sourceforge.net/Main_Page) with [NsProcess plugin](http://nsis.sourceforge.net/NsProcess_plugin) is required to build installer. To build installer run build script with **-Setup** parameter:
``` .\build.ps1 -Setup ```

Portable zip package can be built when using **-Portable** parameter.

## Development environment

`Debug` builds are configured to throw exceptions even in cases where `Release` builds would log error message. This is mainly for cases where Playnite can recover and still work properly, but indicates some issue that should be investigated. If you want to suppress these exceptions with `Debug` builds then edit `App.Debug.config` and set `ThrowAllErrors` to `False`.

## Playnite Services deployment
Several Playnite features are depended on separate Playnite service. Specifically:
* Steam library import
* Steam metadata download
* IGDB integration
* Patreon integration

To deploy your own services instance:
* Build **PlayniteServices** project, either manually from VS, using **buildServices.ps1** script or via ```dotnet publish```
* Create configuration file `customSettings.json` inside service folder
* Specify content of `customSettings.json` based on `appsettings.json`. For example adding your own Steam API key will look like this:
```
  "Steam": {
    "ApiKey": "customapikeyhere"
  }
```
* You need provide your own API keys and other values for all empty fields from `appsettings.json`
* Deploy project to [web server](https://docs.microsoft.com/en-us/aspnet/core/publishing/) or run it directly via ```dotnet .\PlayniteServices.dll```
* Configure root endpoint inside `App.Debug.config` file via `ServicesUrl` key.

**DO NOT run let development builds connect to production service instance. This might potentially lead to serious issues causing problems to all users!**

### Auto-Update
Requires simple web server serving `update.json` file with information about available version. URL with update.json has to be configured in `App.Debug.config` file via `UpdateUrl` key.

Example file:
```
{
    "stable" : {
        "version" : "0.70.0.0",
        "url" : "https://localhost/build/PlayniteInstaller.exe"
    }
}
```