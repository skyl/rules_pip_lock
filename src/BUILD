package(default_visibility = ["//visibility:public"])

load("@rules_python//python:defs.bzl", "py_binary")
load("@piptool_deps//:requirements.bzl", "requirement")
load("@piptool_deps_3//:requirements.bzl", requirement_3 = "requirement")
load("@subpar//:subpar.bzl", "par_binary")

py_library(
    name = "whllib",
    srcs = ["whl.py"],
    deps = select(
        {
            "@bazel_tools//tools/python:PY2": [
                requirement("pip"),
                requirement("pkginfo"),
                requirement("setuptools"),
                requirement("wheel"),
            ],
            "@bazel_tools//tools/python:PY3": [
                requirement_3("pip"),
                requirement_3("pkginfo"),
                requirement_3("setuptools"),
                requirement_3("wheel"),
            ],
        },
    ),
)

par_binary(
    name = "whl",
    srcs = ["whl.py"],
    python_version = "PY2",
    deps = [
        ":whllib",
    ],
    zip_safe = True,
)

par_binary(
    name = "piptool",
    srcs = ["piptool.py"],
    python_version = "PY2",
    deps = [
        requirement("pip"),
    ],
)

par_binary(
    name = "compile",
    srcs = ["compile.py"],
    python_version = "PY2",
    deps = [
        requirement("pip-tools"),
        requirement("pip"),
        requirement("setuptools"),
        requirement("wheel"),
    ],
)
