# Code Ready Containers

CodeReady Containers is a tool that manages a local OpenShift 4.x cluster optimized for testing and development purposes

Usage:
``
  crc [flags]
  crc [command]
```
Available Commands:
```
  config      Modify crc configuration
  console     Open the OpenShift Web Console in the default browser
  delete      Delete the OpenShift cluster
  help        Help about any command
  ip          Get IP address of the running OpenShift cluster
  oc-env      Add the 'oc' binary to PATH
  setup       Set up prerequisites for the OpenShift cluster
  start       Start the OpenShift cluster
  status      Display status of the OpenShift cluster
  stop        Stop the OpenShift cluster
  version     Print version information
```
Flags:
```
  -f, --force              Forcefully perform an action
  -h, --help               help for crc
      --log-level string   log level (e.g. "debug | info | warn | error") (default "info")
```
Use "crc [command] --help" for more information about a command.

## Customize CRC to optimize your machine avaialble resources