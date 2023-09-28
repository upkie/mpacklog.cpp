# -*- python -*-
#
# Copyright 2022 Stéphane Caron

workspace(name = "mpacklog")

# Dependency: Palimpsest

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "palimpsest",
    remote = "https://github.com/tasts-robots/palimpsest.git",
    commit = "4a2d4935ca3394cb036cfad4c9030d3b22b8cc42",
    shallow_since = "1654192305 +0200"
)

load("@palimpsest//tools/workspace:default.bzl", add_palimpsest_repositories = "add_default_repositories")
add_palimpsest_repositories()
