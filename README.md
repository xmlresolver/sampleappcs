# sampleappcs

A sample application that demonstrates the C# XmlResolver.

This project isn’t (yet) anywhere near as complete or comprehensive as
[the Java version](https://github.com/xmlresolver/sampleapp), but it does
demonstrate how the C# XmlResolver library is used.

## Download and build the app

Running `gradlew dotnetBuild` will build the executable. I assume you
can load the project in your favorite GUI instead and push the build
button.

## Run the app

Parse a document using the local catalog:

```
$ dotnet SampleApp/SampleApp/bin/Release/net5.0/SampleApp.dll -c test/sample.zip test/doc.xml
```

Except, of course, that this seem to fail somewhat mysteriously. :-(

It works when I run it from the IDE though, so possibly something I
don’t understand about how to run C# apps?

