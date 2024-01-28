workspace(name = "one_shot_prime_sieve")

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository", "new_git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

BACKWARD_CPP_BUILD = """
cc_library(
    name = "plog",
    hdrs = glob([
        "plog/*.h",
        "plog/**/*.h",
    ]),
    includes = [
        ".",
    ],
    visibility = ["//visibility:public"],
)
"""

new_git_repository(
    name = "plog",
    build_file_content = BACKWARD_CPP_BUILD,
    # tag = "1.1.5",
    commit = "f4c22b03d5d3aa753cca8e716636ac4eb29b0917",
    remote = "https://github.com/SergiusTheBest/plog",
    shallow_since = "1571659313 +0300",
    strip_prefix = "include",
)

BACKWARD_CPP_BUILD = """
cc_library(
    name = "backward",
    hdrs = ["backward.hpp"],
    visibility = ["//visibility:public"],
    includes = ["include"],
)
"""

new_git_repository(
    name = "backward-cpp",
    build_file_content = BACKWARD_CPP_BUILD,
    commit = "83da75636cef3ee6e0c83cf8651e2929e1b87261",
    remote = "git@github.com:bombela/backward-cpp.git",
    shallow_since = "1586831088 -0700",
)