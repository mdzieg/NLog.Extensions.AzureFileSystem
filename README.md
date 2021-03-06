# NLog.Extensions.AzureFileSystem
NLog target for Azure file system (file shares)

[![Build status](https://ci.appveyor.com/api/projects/status/3u2517drfngeswe0?svg=true)](https://ci.appveyor.com/project/lucianaparaschivei/nlog-extensions-azurefilesystem)

[![NuGet version (NLog.Extensions.AzureFileSystem)](https://img.shields.io/nuget/v/NLog.Extensions.AzureFileSystem.svg?style=flat-square)](https://www.nuget.org/packages/NLog.Extensions.AzureFileSystem/)

![Nuget download (NLog.Extensions.AzureFileSystem)](https://img.shields.io/nuget/dt/NLog.Extensions.AzureFileSystem)

## Usage

  - StorageConnectionString (required): Azure storage connection string
  - AzureFileShareName (required): Azure file system share name
  - AzureFileShareFolder (required): Folder in which the logs are created
  - AzureFileName (required): File name pattern for log files

## Sample Configuration

```xml
<extensions>
  <add assembly="NLog.Extensions.AzureFileSystem"/>
</extensions>

<targets async="true">
    <target type="AzureFileSystem"
            name="ownFile"
            layout="${verbose}"
            StorageConnectionString="DefaultEndpointsProtocol=https;AccountName=;AccountKey=;EndpointSuffix="
            AzureFileShareName="demo-app"
            AzureFileShareFolder="ownLogs"
            AzureFileName="nlog-own-${processid}-${shortdate}.log" />
</targets>
```
