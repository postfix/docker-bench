[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Docker-bench is a Go application that checks whether Docker is deployed securely by running the checks documented in the [CIS Docker Benchmark](https://www.cisecurity.org/benchmark/docker/).

Tests are configured with YAML files, making this tool easy to update as test specifications evolve. 


## CIS Docker Benchmark support

docker-bench currently supports tests for multiple versions of Docker (1.13, and 17.06).
docker-bench will determine the test set to run based on the Docker version running on the host machine. 
The version to run tests for can also be specified manually with the `--version <ver>` commandline flag.

## Installation
### Installing from sources

Install [Go](https://golang.org/doc/install), then
clone this repository and run as follows (assuming your [$GOPATH is set](https://github.com/golang/go/wiki/GOPATH)):

```shell
go get github.com/aquasecurity/docker-bench
cd $GOPATH/src/github.com/aquasecurity/docker-bench
go build -o docker-bench .

# See all supported options
./docker-bench --help

# Run checks
./docker-bench

# Run checks for specified Docker version
./docker-bench --version 1.13.0

```

# Tests
Tests are specified in definition files `cfg/<version>/definitions.yaml.
Where `<version>` is the version of docker for which the test applies.

# Contributing
We welcome PRs and issue reports. 
