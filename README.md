# Patton

## Setup

### Prerequisites

- zstd
- Docker

### Install

```sh
wget https://raw.githubusercontent.com/BBVA/patton/develop/bin/patton
sudo install patton /usr/local/bin
```

## Usage

```console
$ patton --help
Usage: patton [OPTION]... [PATTERN]
Try '/usr/local/bin/patton -h|--help' for more information
  -h, --help           display this help text and exit
  -V, --version        display version information and exit
  -d, --database-file  path to database file
  -t, --search-type    type of search to execute: product|pkg_debian|pkg_ubuntu|pkg_rhel|fulltext
  -s, --search-subtype for search-type:(debian|ubuntu), sets the suite
    e.g.: buster, potato, fossa, xenial, precise, trusty...
  -v, --pkg-version    cpe version when searching by cpe
  -n, --pkg-name       path to database file
  -w, --pkg-vendor     path to database file

```

### Debian

```sh
patton -t pkg_debian < /var/lib/dpkg/status
```

### Ubuntu

```sh
patton -t pkg_ubuntu < /var/lib/dpkg/status
```

### Red Hat Enterprise Linux

```sh
patton -t pkg_rhel
```
**NOTE**: Have to be run on RHEL 8 or newer

### Fulltext search

```sh
wget https://github.com/BBVA/patton/releases/download/latest/patton.db.zst
patton -d patton.db.zst -t fulltext openssl
```

## TODO

- [ ] rename scanners/debian to scanners/debian-debsecan consistently
