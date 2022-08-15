---
template: Default
title: Installing Chloroplast
---

## Dependencies

You must have the `dotnet` CLI installed. To do so, you only need to install _.NET Core_ on your machine. The instructions for that can be found here for your respective operating system.

https://docs.microsoft.com/en-us/dotnet/core/install/

## Installing Chloroplast

You can acquire chloroplast by installing it as either a [local or global 
tool](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-tool-install).

### Wilderness Labs package registry

Currently, Chloroplast is distributed only through the wilderness labs package
registry. This means you'll need to add the authenticated nuget source as follows, replacing `<< your GitHub username >>` and `<< a GitHub personal access token >>`.

If you need a [GitHub personal access token](https://github.com/settings/tokens/new), generate one with `read:packages` permission.

```console
dotnet nuget add source https://nuget.pkg.github.com/WildernessLabs/index.json --name "Wilderness Labs" --username << your GitHub username >> --password << a GitHub personal access token >>
```

### Global

With that installed you can install Chloroplast as a global tool.

```console
dotnet tool install Chloroplast.Tool --global
```

If you install it as a global tool, you can invoke it with the tool name
`chloroplast`.

### Local

Or alternatively, you can install it as a local tool by first creating a local
tool manifest in the project folder, as follows:

```console
dotnet new tool-manifest
dotnet tool install Chloroplast.Tool
```

If you install it as a local tool, you must prefix the tool name, so you can invoke it with `dotnet chloroplast`.

## Updating

You can update to the latest release at any point by running the following command (with or without the `--global` depending on your preference):

```console
dotnet tool update Chloroplast.Tool --global
```
