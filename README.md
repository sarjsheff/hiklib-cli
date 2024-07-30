# hiklib-cli

```
# hiklib-cli help
Console app for connect to hikvision camera.

Usage:
  hiklib-cli [flags]
  hiklib-cli [command]

Available Commands:
  completion  Generate the autocompletion script for the specified shell
  download    Download video from camera.
  help        Help about any command
  list        Get a list of saved videos from the camera in this month.
  snapshot    Get snapshot from camera.
  version     Print the version number of Hikvision SDK

Flags:
  -h, --help      help for hiklib-cli
  -v, --verbose   verbose output

Use "hiklib-cli [command] --help" for more information about a command.
```

# build

```
docker run --platform linux/amd64 -it --rm -v $(pwd)/gocache/pkg:/go/pkg -v $(pwd)/gocache/go-build:/root/.cache/go-build  -v $(pwd)/EN-HCNetSDKV6.1.9.48_build20230410_linux64:/hiksdk -v $(pwd):/app -w /app -e LD_LIBRARY_PATH="/hiksdk/lib" -e CGO_CXXFLAGS="-I/hiksdk/incEn/" -e CGO_LDFLAGS="-L/hiksdk/lib -lhcnetsdk" golang go build cmd/hiklib-cli/hiklib-cli.go
```

For cleaning cache delete `gocache` directory.