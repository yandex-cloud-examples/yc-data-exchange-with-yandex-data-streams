# Exchanging data through Yandex Data Streams

This use case demonstrates a simple way for your apps to interact through Yandex Data Streams:
* __Producer__ sends data to a data stream.
* __Consumer__ reads data from the stream.
* __Shared__ is a shared library of classes.

## Installing the packages

AWSSDK.Kinesis, SDK for .NET package for Amazon Kinesis, compatible with Yandex Data Streams:

```
Install-Package AWSSDK.Kinesis
```

Packages for loading the configuration:
```
Install-Package Microsoft.Extensions.Configuration
Install-Package Microsoft.Extensions.Configuration.Json
```

## Configuration

1. [Create a stream](https://yandex.cloud/en/docs/data-streams/operations/manage-streams).
1. [Create a service account](https://yandex.cloud/en/docs/data-streams/quickstart/).
1. Edit `appsettings.json` as follows:

    * `YC_Key_ID`: Static access key. Replace _***_ with the key from step 2.
    * `YC_Key_secret`: Static access key secret. Replace _***_ with the secret from step 2.
    * `serviceURL`: `https://yds.serverless.yandexcloud.net`.
    * `region`: _ru-central1_.
    * `folder`: ID of the folder that houses your stream, e.g., `b1g82kppqsd2m076av7h`.
    * `database`: ID of the Yandex Managed Service for YDB database that houses the stream, e.g., `etnp67d2bn66i70i0qav`.
    * `streamName`: Name of your stream, e.g., `yads`.

```json
{
  "YandexCloudDataStreamConfiguration": {
    "YC_Key_ID": "***",
    "YC_Key_secret": "***",
    "serviceURL": "https://yds.serverless.yandexcloud.net",
    "region": "ru-central1",
    "folder": "b1g82kppqsd2m076av7h",
    "database": "etnp67d2bn66i70i0qav",
    "streamName": "yads"
  }
}
```

