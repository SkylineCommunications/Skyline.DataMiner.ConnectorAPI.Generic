# Skyline.DataMiner.ConnectorAPI.Generic

## About

### About Skyline.DataMiner.ConnectorAPI.Generic

Skyline.DataMiner.ConnectorAPI.Generic is a NuGet package that provides reusable Inter-App message types for generic DataMiner integrations that exchange a raw string payload.

The package contains:

* `RawDataMessage`, an Inter-App message with a `string MessageValue` payload.
* `RawDataMessageResult`, a result message with a `bool DeliveredSuccessfully` property.
* `InterApp.KnownTypes`, the supported message types for serialization and deserialization.

`MessageValue` carries the raw payload. An empty string represents an intentionally empty payload; `null` means the value was not assigned.

> Documentation: [InterAppCalls](https://docs.dataminer.services/develop/devguide/ClassLibrary/ClassLibraryInterAppClasses.html)

### About DataMiner

DataMiner is a transformational platform that provides vendor-independent control and monitoring of devices and services. Out of the box and by design, it addresses key challenges such as security, complexity, multi-cloud, and much more. It has a pronounced open architecture and powerful capabilities enabling users to evolve easily and continuously.

The foundation of DataMiner is its powerful and versatile data acquisition and control layer. With DataMiner, there are no restrictions to what data users can access. Data sources may reside on premises, in the cloud, or in a hybrid setup.

A unique catalog of 7000+ connectors already exists. In addition, several public NuGet packages are available to help build connectors (also known as "protocols" or "drivers").

### About Skyline Communications

At Skyline Communications, we deal in world-class solutions that are deployed by leading companies around the globe. Check out [our proven track record](https://aka.dataminer.services/about-skyline) and see how we make our customers' lives easier by empowering them to take their operations to the next level.

## Requirements

The package targets **.NET Framework 4.6.2** and depends on [`Skyline.DataMiner.Core.InterAppCalls.Common`](https://www.nuget.org/packages/Skyline.DataMiner.Core.InterAppCalls.Common). The dependency is restored transitively when installing this package with NuGet.

For connector development in Visual Studio, install the [DataMiner Integration Studio](https://aka.dataminer.services/DisInstallation) extension. Use `PackageReference` to consume NuGet packages; DIS is designed to work with PackageReferences. For information about migrating from `packages.config`, see [Migrate from packages.config to PackageReference](https://learn.microsoft.com/nuget/consume-packages/migrate-packages-config-to-package-reference).

## Getting started

Install the package from NuGet:

```shell
dotnet add package Skyline.DataMiner.ConnectorAPI.Generic
```

Create a message with the raw payload and use the provided known types when configuring Inter-App serialization and deserialization:

```csharp
using Skyline.DataMiner.ConnectorAPI.Generic;

var message = new RawDataMessage
{
    MessageValue = "{\"status\":\"ok\"}",
};

var supportedTypes = InterApp.KnownTypes;
```

`InterApp.KnownTypes` contains both `RawDataMessage` and `RawDataMessageResult`.

## License

This package includes the [Skyline Library License](https://github.com/SkylineCommunications/Skyline.DataMiner.ConnectorAPI.Generic/blob/main/ConnectorAPI/LICENSE.txt). It permits use only for the development, testing, and validation of DataMiner packages and components; other use requires prior written authorization from Skyline Communications.

## Repository

Source code and issue tracking: [SkylineCommunications/Skyline.DataMiner.ConnectorAPI.Generic](https://github.com/SkylineCommunications/Skyline.DataMiner.ConnectorAPI.Generic).
