# sampleappcs

A sample application that demonstrates the C# XmlResolver.

This project isn’t (yet) anywhere near as complete or comprehensive as
[the Java version](https://github.com/xmlresolver/sampleapp), but it does
demonstrate how the C# XmlResolver library is used.

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
