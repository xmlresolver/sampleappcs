# sampleappcs

A sample application that demonstrates the C# XmlResolver.

This project isn’t (yet) anywhere near as complete or comprehensive as
[the Java version](https://github.com/xmlresolver/sampleapp), but it does
demonstrate how the C# XmlResolver library is used.

These few lines are the important bit:

```
// Create a configuration object
XmlResolverConfiguration config = new XmlResolverConfiguration();

// If your application references assemblies that have embedded catalogs,
// add them to the configuration:
config.SetFeature(ResolverFeature.ASSEMBLY_CATALOG, "XmlResolverData.dll");

// Add any other relevant catalogs:
config.AddCatalog("./catalog.xml");

// Create a resolver
Resolver resolver = new Resolver(config);

// Configure the System.XmlReader to use your resolver
XmlReaderSettings settings = new XmlReaderSettings();
settings.XmlResolver = resolver;

// Parse your file(s)…
```

## Download and build the app

Running `gradlew dotnetBuild` will build the executable.
Alternatively, load the project in your favorite GUI instead and push
the build button.

## Run the app

As far as I can tell, you’re meant to run .NET applications with the `dotnet` command.

Furthermore, it seems to be the case that some application behaviors depend on starting
the application from the directory that contains the DLL.

Use whatever shell command is appropriate to change to the
`SampleApp/SampleApp/bin/Release/net5.0` directory.

Parse a document using the local catalog:

```
$ dotnet SampleApp.dll -c ../../../../../test/sample.zip ../../../../../test/doc.xml
Parsing ../../../../../test/doc.xml
Using catalogs: ./catalog.xml, ../../../../../test/sample.zip, pack://application:,,,XmlResolverData;0.0.4.0;component/Org.XmlResolver.catalog.xml
Counted 24 items in the document.
```
