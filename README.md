# Chloroplast Docs

The documentation for Chloroplast built using Chloroplast itself, both templated content files and API documentation.

## Building locally

To build the Chloroplast docs site in this repo, you'll need a few prerequisites.

* Monodoc (mdoc) output of the Chloroplast.Core library in `\tmp\EcmaXml`, generated from within the [Chloroplast tool repo](https://github.com/WildernessLabs/Chloroplast).
* Chloroplast installed as a .NET tool (`dotnet`).

### Building the Chloroplast mdoc output

Open an instance of the Visual Studio Developer Command Prompt (e.g., Developer Command Prompt for VS 2022 from the Start Menu) and run the following commands from the Chloroplast repo checked out locally:

```console
dotnet restore mdocbuild.csproj
msbuild mdocbuild.csproj /t:mdocupdate
```

### Installing the Chloroplast tool

To install Chloroplast as a global tool, run the following command:

```console
dotnet tool install Chloroplast.Tool --global
```

### Build the Chloroplast Documentation site

Once installed, you can build the docs by running the following command:

```console
chloroplast build
```

This will generate the documentation site static HTML files in the `out` folder. You can copy those to a static file host or run them locally with Chloroplast using the following command:

```console
chloroplast host
```

This will launch the resulting static files from a localhost web server.
