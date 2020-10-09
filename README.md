
# Docker Rails Lambda Test Project

A simple Rails Lambda Project on Docker to test Mac filesystems (https://github.com/docker/roadmap/issues/7) benchmarks for the Docker team. Details include:

* Rails v6
* Ruby 2.7
* AWS SAM base Docker image.
* Installs Node and yarn.

## Setup

First run these two commands to build the local image and install dependencies.

```shell
$ ./bin/bootstrap
$ ./bin/setup
```

## Benchmark

I am interested in measuring how fast Rails can boot.

```shell
$ ./bin/console
```

| Edge2.3.4.0 (mutagen) | Edge2.4.1.0 (gRPC-FUSE) |
| :-------------------: | :---------------------: |
|           3s          |           34s           |

* MacBook Pro (13-inch, 2019, Four Thunderbolt 3 ports)
* 2.8 GHz Quad-Core Intel Core i7
