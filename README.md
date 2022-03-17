# Docker Rails Lambda Test Project

A simple Rails Lambda Project on Docker to test Mac filesystems (https://github.com/docker/roadmap/issues/7) benchmarks for the Docker team. Details include:

- Rails v6
- Ruby 2.7
- AWS SAM base Docker image.
- Installs Node and yarn.

## Setup

First run these two commands to build the local image and install dependencies.

```shell
$ ./bin/bootstrap
$ ./bin/setup
```

## Benchmark

I am interested in measuring how fast Rails can boot.

- MacBook Pro (13-inch, 2019, Four Thunderbolt 3 ports)
- 2.8 GHz Quad-Core Intel Core i7
- Monterey (starting with 4.3.0)

```shell
$ ./bin/console
```

#### Stable:

| 4.6.0 (gRPC-FUSE) | 3.5.2 (VirtuoFS) |
| :---------------: | :--------------: |
|       >90s        |       11s        |

| 4.3.0.71111 (VirtuoFS) |
| :--------------------: |
|          30s           |

| 3.5.2 (osxfs) | 3.5.2 (gRPC-FUSE) |
| :-----------: | :---------------: |
|      22s      |        35s        |

| 3.3.1 (osxfs) | 3.3.1 (gRPC-FUSE) |
| :-----------: | :---------------: |
|      33s      |        33s        |

| 3.2.1 (osxfs) | 3.2.1 (gRPC-FUSE) |
| :-----------: | :---------------: |
|      15s      |        32s        |

| 3.0.3 (osxfs) | 3.0.3 (gRPC-FUSE) |
| :-----------: | :---------------: |
|      19s      |        36s        |

(update to big sir)

| 3.0.0 (osxfs) | 3.0.0 (gRPC-FUSE) |
| :-----------: | :---------------: |
|      16s      |        45s        |

| 2.5.0.1 (osxfs) | 2.5.0.1 (gRPC-FUSE) |
| :-------------: | :-----------------: |
|       16s       |         35s         |

| 2.4.0.0 (osxfs) | 2.4.0.0 (gRPC-FUSE) |
| :-------------: | :-----------------: |
|       20s       |         33s         |

#### Edge:

| 2.3.4.0 (mutagen) | 2.4.1.0 (gRPC-FUSE) | 2.5.1.0 (gRPC-FUSE) |
| :---------------: | :-----------------: | :-----------------: |
|        3s         |         34s         |         52s         |
