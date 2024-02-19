# dotnet-sdk versions tap

[![Continuous-integration](https://github.com/isen-ng/homebrew-dotnet-sdk-versions/actions/workflows/ci.yml/badge.svg)](https://github.com/isen-ng/homebrew-dotnet-sdk-versions/actions/workflows/ci.yml)
[![Auto-updater](https://github.com/isen-ng/homebrew-dotnet-sdk-versions/actions/workflows/auto-updater.yml/badge.svg)](https://github.com/isen-ng/homebrew-dotnet-sdk-versions/actions/workflows/auto-updater.yml)
[![Auto-committer](https://github.com/isen-ng/homebrew-dotnet-sdk-versions/actions/workflows/auto-commit.yml/badge.svg)](https://github.com/isen-ng/homebrew-dotnet-sdk-versions/actions/workflows/auto-commit.yml)

This tap contains different versions that you can install in parallel to the latest version provided by the
[official cask](https://github.com/Homebrew/homebrew-cask/blob/master/Casks/d/dotnet-sdk.rb).

Install one of the previous versions by tapping this repository and running the install command.


## Installing one of the versions here

```
brew tap isen-ng/dotnet-sdk-versions
brew install --cask <version>

dotnet --list-sdks
```


### Versions

| Version             | .NET SDK | Arch        | Remarks                                  |
| ------------------- | -------- | ----------- | ---------------------------------------- |
| `dotnet-sdk8-0-100` | 8.0.101  | x64 & arm64 |                                          |
| `dotnet-sdk7-0-400` | 7.0.406  | x64 & arm64 |                                          |
| `dotnet-sdk7-0-300` | 7.0.306  | x64 & arm64 |                                          |
| `dotnet-sdk7-0-200` | 7.0.203  | x64 & arm64 |                                          |
| `dotnet-sdk7-0-100` | 7.0.102  | x64 & arm64 |                                          |
| `dotnet-sdk6-0-400` | 6.0.419  | x64 & arm64 |                                          |
| `dotnet-sdk6-0-300` | 6.0.303  | x64 & arm64 |                                          |
| `dotnet-sdk6-0-200` | 6.0.202  | x64 & arm64 |                                          |
| `dotnet-sdk6-0-100` | 6.0.108  | x64 & arm64 |                                          |
| `dotnet-sdk5-0-400` | 5.0.408  | x64         | When installed on arm64, use `dotnetx64` |
| `dotnet-sdk5-0-200` | 5.0.209  | x64         | When installed on arm64, use `dotnetx64` |
| `dotnet-sdk3-1-400` | 3.1.426  | x64         | When installed on arm64, use `dotnetx64` |
| `dotnet-sdk3-1-300` | 3.1.302  | x64         |                                          |
| `dotnet-sdk3-1-200` | 3.1.202  | x64         |                                          |
| `dotnet-sdk3-1-100` | 3.1.120  | x64         |                                          |
| `dotnet-sdk3-0-100` | 3.0.103  | x64         |                                          |
| `dotnet-sdk2-2-400` | 2.2.402  | x64         |                                          |
| `dotnet-sdk2-2-300` | 2.2.301  | x64         |                                          |
| `dotnet-sdk2-2-200` | 2.2.207  | x64         |                                          |
| `dotnet-sdk2-2-100` | 2.2.110  | x64         |                                          |
| `dotnet-sdk2-1-800` | 2.1.818  | x64         |                                          |
| `dotnet-sdk2-1-500` | 2.1.526  | x64         |                                          |
| `dotnet-sdk2-1-400` | 2.1.403  | x64         |                                          |

**Note**: Installing .NET SDK 5 using this tap or the official package from Microsoft will uninstall all other
.NET SDKs on your machine. To overcome this you'll need to re-install the SDK versions you want from this tap
after installing/upgrading to .NET SDK 5.


### Preview versions

| Version               | .NET SDK                   | Arch        | Remarks |
| --------------------- | -------------------------- | ----------- | ------- |
| `dotnet-sdk9-preview` | 9.0.100-preview.1.24101.2  | x64 & arm64 |         |
| `dotnet-sdk8-preview` | 8.0.101-rc.2.23502.2       | x64 & arm64 |         |
| `dotnet-sdk7-preview` | 7.0.100-rc.2.22477.23      | x64 & arm64 |         |

**Note**: Preview versions is a newly supported feature (as of September 2022). Please send feedback/create issues
if there are problems with the compatibility of the preview versions.


## Uninstalling

Because the .NET SDK packages uses shared dependencies between different versions, it is unwise to delete these
dependencies when uninstalling a particular version as it will cause other versions not to work.

If there is a need to purge these dependencies, use the `zap` flag:

```
brew uninstall --zap --cask <version>
```

*Important*: Uninstalling the offical version will also remove these dependencies, so you'll need to reinstall the
particular version you want to use again.


## Using a particular version

The `dotnet` command will automatically use the latest appropriate version unless specified by a
[global.json](https://docs.microsoft.com/en-us/dotnet/core/tools/global-json).
