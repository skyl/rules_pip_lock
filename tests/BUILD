package(default_visibility = ["//visibility:public"])

load("@rules_python//python:defs.bzl", "py_binary", "py_test")
load("@piptool_deps_tests//:requirements.bzl", "requirement")
load("@piptool_deps_tests_3//:requirements.bzl", requirement_3 = "requirement")

py_test(
    name = "whl_test2",
    srcs = ["whl_test.py"],
    data = [
        "@futures_2_2_0_whl//file",
        "@futures_3_1_1_whl//file",
        "@google_cloud_language_whl//file",
        "@grpc_whl//file",
        "@mock_whl//file",
    ],
    main = "whl_test.py",
    python_version = "PY2",
    deps = [
        "//src:whllib",
        requirement("mock"),
    ],
)

py_test(
    name = "whl_test3",
    srcs = ["whl_test.py"],
    data = [
        "@futures_2_2_0_whl//file",
        "@futures_3_1_1_whl//file",
        "@google_cloud_language_whl//file",
        "@grpc_whl//file",
        "@mock_whl//file",
    ],
    main = "whl_test.py",
    python_version = "PY3",
    deps = [
        "//src:whllib",
        requirement_3("mock"),
        # not need, just here for testing it can be installed
        requirement_3("pytest"),
    ],
)

py_test(
    name = "namespace_test",
    srcs = ["namespace_test.py"],
    deps = [
        requirement("google-cloud-language"),
        requirement("testing.postgresql"),
        requirement("testing.mysqld"),
    ],
    python_version = "PY2",
)
