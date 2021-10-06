## Building

Visual Studio 2017/2019 and .NET SDK 4.6.2 is required to build the application.

For building inside VS make sure you are switched to `x86` solution configuration.

## Development environment

`Debug` builds are configured to throw exceptions even in cases where `Release` builds would log error message. This is mainly for cases where Playnite can recover and still work properly, but indicates some issue that should be investigated. If you want to suppress these exceptions with `Debug` builds then edit `Common.config` and set `ThrowAllErrors` to `False`.

## Fullscreen mode development
Fullscreen mode uses [custom font files](https://assetstore.unity.com/packages/2d/gui/icons/xbox-one-playstation-4-buttons-pack-77916) that can't be redistributed with Playnite's source. If you want to develop/build Fullscreen mode, then you have to obtain your own license or replace them with compatible ones.

## Playnite Services deployment
Several Playnite features depended on a separate Playnite service. Specifically:
* Steam library import
* IGDB integration
* Patreon integration

**DO NOT run let development builds connect to production service instance. This might potentially lead to serious issues causing problems to all users!**

Backend project can be found in a [separate repository](https://github.com/JosefNemec/PlayniteBackend), .NET Core 3.1 and MongoDB are required.

You will need to provide your own Twitch API keys (IGDB is owned by Twitch) in app settings file for IGDB integration to work.