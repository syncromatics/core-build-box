# syncromatics/core-build-box

This is a Docker image to do .NET builds (.NET Core) for various Syncromatics projects.

## Installed tools, utilities, and packages

### .NET Core 2.0

This image is based on the `microsoft/dotnet:2-sdk` Docker image, so it includes all of the .NET Core SDK tools in that image.

### Cake Build

A Cake build script and several commonly-used tools and addins are pre-installed. The build script is availale on the PATH as `cake` and the following tools and addins are installed:

* Cake.Compression
* Cake.Docker
* Cake.FileHelpers
* Cake.Git
    * Note: this image is built with a workaround for using the system-installed `libgit2` binary instead of the package-installed version.
* Cake.Testing
* SharpZipLib
* xunit.runner.console

The tools directory is located at `/build/tools`.

When running a Cake target inside this container, use `cake` instead of your repo's copy of `build.sh`. (i.e., `cake -t TargetName`)
