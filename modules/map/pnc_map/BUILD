load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "path",
    srcs = [
        "path.cc",
    ],
    hdrs = [
        "path.h",
    ],
    deps = [
        "//modules/common/math",
        "//modules/map/hdmap",
        "//modules/map/proto:map_proto",
        "//modules/routing/proto:routing_proto",
    ],
)

cc_library(
    name = "pnc_map",
    srcs = [
        "pnc_map.cc",
    ],
    hdrs = [
        "pnc_map.h",
    ],
    deps = [
        "//external:gflags",
        "//modules/map/hdmap",
        "//modules/map/pnc_map:path",
    ],
)

cc_test(
    name = "pnc_path_test",
    size = "small",
    srcs = [
        "path_test.cc",
    ],
    deps = [
        ":path",
        "//modules/common:log",
        "//modules/common/time",
        "//modules/common/util",
        "@gtest//:main",
    ],
)

filegroup(
    name = "testdata",
    srcs = glob([
        "testdata/**",
    ]),
)

cc_test(
    name = "pnc_map_test",
    size = "small",
    srcs = [
        "pnc_map_test.cc",
    ],
    data = [
        ":testdata",
        "//modules/map:map_data",
    ],
    deps = [
        ":pnc_map",
        "//modules/common:log",
        "//modules/common/time",
        "//modules/common/util",
        "@gtest//:main",
    ],
)

cpplint()
