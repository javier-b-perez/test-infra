package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_binary",
    "go_library",
    "go_test",
)

go_binary(
    name = "splice",
    importpath = "k8s.io/test-infra/prow/cmd/splice",
    library = ":go_default_library",
)

go_test(
    name = "go_default_test",
    srcs = ["main_test.go"],
    importpath = "k8s.io/test-infra/prow/cmd/splice",
    library = ":go_default_library",
    deps = [
        "//prow/config:go_default_library",
        "//prow/kube:go_default_library",
    ],
)

go_library(
    name = "go_default_library",
    srcs = ["main.go"],
    importpath = "k8s.io/test-infra/prow/cmd/splice",
    deps = [
        "//prow/config:go_default_library",
        "//prow/kube:go_default_library",
        "//prow/pjutil:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
)
