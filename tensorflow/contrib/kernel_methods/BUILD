# Description:
#   Contains kernel methods for TensorFlow.

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

package(default_visibility = ["//visibility:public"])

load("//tensorflow:tensorflow.bzl", "py_test")

py_library(
    name = "kernel_methods",
    srcs = [
        "__init__.py",
        "python/kernel_estimators.py",
        "python/mappers/random_fourier_features.py",
    ],
    srcs_version = "PY2AND3",
    deps = [
        ":dense_kernel_mapper_py",
        "//tensorflow/contrib/layers:layers_py",
        "//tensorflow/contrib/learn",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform",
        "//tensorflow/python:util",
        "//third_party/py/numpy",
        "@six_archive//:six",
    ],
)

py_library(
    name = "dense_kernel_mapper_py",
    srcs = ["python/mappers/dense_kernel_mapper.py"],
    srcs_version = "PY2AND3",
    deps = ["@six_archive//:six"],
)

py_test(
    name = "random_fourier_features_test",
    srcs = ["python/mappers/random_fourier_features_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":dense_kernel_mapper_py",
        ":kernel_methods",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:random_ops",
    ],
)

py_test(
    name = "kernel_estimators_test",
    srcs = ["python/kernel_estimators_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":kernel_methods",
        "//tensorflow/contrib/layers:layers_py",
        "//tensorflow/contrib/learn",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:sparse_tensor",
        "//third_party/py/numpy",
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
