# Description:
#   Contains kernels for layers.

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "sparse_feature_cross_kernel",
    srcs = ["sparse_feature_cross_kernel.cc"],
    deps = [
        "//tensorflow/core:framework_headers_lib",
        "//third_party/eigen3",
        "@farmhash_archive//:farmhash",
        "@com_github_google_protobuf//:protobuf_headers",
    ],
    alwayslink = 1,
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
)
