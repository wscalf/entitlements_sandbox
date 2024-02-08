# Entitlements Sandbox

## Purpose
Quickly and easily launch a preconfigured test instance of SpiceDB for demoing and testing with the entitlements sub-schema. This package includes schema and test data.

## Prereqs
* docker-compose
* A SpiceDB [client library](https://github.com/authzed/awesome-spicedb?tab=readme-ov-file#official-libraries) for your programming language
* (Optional) the [zed cli client](https://github.com/authzed/zed/releases/tag/v0.16.4)

## Getting Started
Run `docker-compose up`, which will download and launch a preconfigured SpiceDB instance running in non-TLS mode on port 50051 with the shared access key "sharedkey"

If the Zed client is installed, you can test whether the system is running correctly with the command: ```zed permission lookup-subjects content/host:greeter provide_content content/repository --endpoint localhost:50051 --token sharedkey --insecure```, which should display: 
```
content/repository:awesomeos
content/repository:hello
```

## Client Integration
Connectivity: use the connection settings above (endpoint: localhost:50051, token: sharedkey, TLS: none). See your client library documentation for specifics.

Use the lookup-subjects operation to resolve which repositories are available to a given host, as above.

[Full API Reference](https://buf.build/authzed/api/docs/main:authzed.api.v1)