# mpacklog.cpp

[![Build](https://img.shields.io/github/actions/workflow/status/tasts-robots/mpacklog.cpp/bazel.yml?branch=main)](https://github.com/tasts-robots/mpacklog.cpp/actions)
[![Coverage](https://coveralls.io/repos/github/tasts-robots/mpacklog.cpp/badge.svg?branch=main)](https://coveralls.io/github/tasts-robots/mpacklog.cpp?branch=main)
[![Documentation](https://img.shields.io/badge/docs-online-brightgreen?logo=read-the-docs&style=flat)](https://scaron.info/doc/mpacklog/)
![C++ version](https://img.shields.io/badge/C++-17/20-blue.svg?style=flat)
[![C++ release](https://img.shields.io/github/v/release/tasts-robots/mpacklog.cpp.svg?sort=semver)](https://github.com/tasts-robots/mpacklog.cpp/releases)

Log dictionaries to MessagePack files in C++.

## Installation

Add a git repository rule to your Bazel ``WORKSPACE``:

```python
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

http_archive(
    name = "mpacklog",
    sha256 = "dfc16f4c1221cb209856d7efc7ebada5ac2f4ea6235127d3ec39de3d3c414a93",
    strip_prefix = "mpacklog-3.0.0",
    url = "https://github.com/tasts-robots/mpacklog.cpp/archive/refs/tags/v3.0.0.tar.gz",
)

load("@mpacklog//tools/workspace:default.bzl", add_mpacklog_repositories = "add_default_repositories")

# This adds dependencies such as @palimpsest for building mpacklog targets
add_mpacklog_repositories()
```

You can then use the ``@mpacklog`` dependency in your C++ targets.

## Usage

The library is multi-threaded. Add messages to the log using the [`put`](https://scaron.info/doc/mpacklog/classmpacklog_1_1Logger.html#af0c278a990b1275b306e89013bb1fac6) function, they will be written to file in the background.

```cpp
#include <mpacklog/Logger.h>
#include <palimpsest/Dictionary.h>

int main() {
    mpacklog::Logger logger("output.mpack");

    for (unsigned bar = 0; bar < 1000u; ++bar) {
        palimpsest::Dictionary dict;
        dict("foo") = bar;
        dict("something") = "else";
        logger.put(dict):
    }
}
```

## See also

* [mpacklog.py](): Sibling Python project with an `mpacklog` command-line tool to manipulate MessagePack files.
* [`jq`](https://github.com/stedolan/jq): manipulate JSON series to add, remove or extend fields.
* [`rq`](https://github.com/dflemstr/rq): transform from/to MessagePack, JSON, YAML, TOML, ...
