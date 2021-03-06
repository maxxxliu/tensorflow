# Description:
#   A small domain-specific language (DSL) for defining deep learning networks.

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

package(default_visibility = ["//visibility:public"])

load("//tensorflow:tensorflow.bzl", "tf_py_test")

py_library(
    name = "specs",
    srcs = [
        "__init__.py",
        "python/__init__.py",
        "python/params_ops.py",
        "python/specs.py",
        "python/specs_lib.py",
        "python/specs_ops.py",
        "python/summaries.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/contrib/layers:layers_py",
        "//tensorflow/contrib/ndlstm",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:logging_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:ops",
        "//tensorflow/python:platform",
        "//tensorflow/python:training",
        "//tensorflow/python:variable_scope",
    ],
)

tf_py_test(
    name = "specs_test",
    srcs = ["python/specs_test.py"],
    additional_deps = [
        ":specs",
        "//third_party/py/numpy",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:init_ops",
        "//tensorflow/python:variables",
    ],
)

tf_py_test(
    name = "summaries_test",
    srcs = ["python/summaries_test.py"],
    additional_deps = [
        ":specs",
        "//third_party/py/numpy",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:variables",
    ],
)

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
        ],
    ),
    visibility = ["//visibility:public"],
)
