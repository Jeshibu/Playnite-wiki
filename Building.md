## Building

Solution will properly load only in Visual Studio 2017 because it contains ASP.NET Core project with .csproj project configuration, which is not supported in 2015. Otherwise there are no other requirements to build from VS, all references should be downloaded from NuGet.

### Build scripts
To build from cmdline run **build.ps1** in PowerShell, script builds Release configuration by default into the same directory. Script accepts *Configuration*, *OutputPath*, *Setup*, *Portable* and *SkipBuild* parameters.

### Building installer
[NSIS 3+](http://nsis.sourceforge.net/Main_Page) with [NsProcess plugin](http://nsis.sourceforge.net/NsProcess_plugin) is required to build installer. To build installer run build script with **-Setup** parameter:
``` .\build.ps1 -Setup ```

Portable zip package can be built when using **-Portable** parameter.

## Development environment

Playnite runs in development environment without extra configuration with exception of Steam library import, IGDB integration and auto-update features.

### Auto-Update
Requires simple web server serving **update.json** file with information about available version. URL with update.json has to be configured in **app.(Debug|Release).config** file, **UpdateUrl** key.

Example file:
```
{
    "stable" : {
        "version" : "0.70.0.0",
        "url" : "https://localhost/build/PlayniteInstaller.exe"
    }
}
```

### Steam import
In order to download information about full Steam library (installed games can be imported without this), Steam API has to be used with proper API key obtained from Valve. Since API access comes with some limitations (1 request per second and 100k requests per day), Playnite doesn't directly access Steam API, but uses caching service. This also prevents distribution of API keys to end users.

To deploy caching service in development environment, you must do following:
* Build **PlayniteServices** project, either manually from VS, using **buildServices.ps1** script or via ```dotnet publish```
* Create configuration file with Steam API key called **customSettings.json** inside service folder (copy empty settings from appsettings.json)
* Deploy project to [web server](https://docs.microsoft.com/en-us/aspnet/core/publishing/) or run it directly via ```dotnet .\PlayniteServices.dll```
* Configure root endpoint inside **app.(Debug|Release).config** file, **ServicesUrl** key.

### IGDB integration
Similarly to Steam integration, IGDB services require API key to be configured in `customSettings.json` file under `IGDB` config section.
