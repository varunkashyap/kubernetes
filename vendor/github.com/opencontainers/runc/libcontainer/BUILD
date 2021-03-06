package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
)

go_library(
    name = "go_default_library",
    srcs = [
        "console.go",
        "container.go",
        "error.go",
        "factory.go",
        "generic_error.go",
        "process.go",
        "stats.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "capabilities_linux.go",
            "compat_1.5_linux.go",
            "console_linux.go",
            "container_linux.go",
            "criu_opts_unix.go",
            "factory_linux.go",
            "init_linux.go",
            "message_linux.go",
            "network_linux.go",
            "notify_linux.go",
            "process_linux.go",
            "restored_process.go",
            "rootfs_linux.go",
            "setgroups_linux.go",
            "setns_init_linux.go",
            "standard_init_linux.go",
            "state_linux.go",
            "stats_linux.go",
        ],
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "console_windows.go",
            "container_windows.go",
            "criu_opts_windows.go",
            "stats_windows.go",
        ],
        "//conditions:default": [],
    }),
    deps = [
        "//vendor/github.com/opencontainers/runc/libcontainer/configs:go_default_library",
        "//vendor/github.com/opencontainers/runc/libcontainer/stacktrace:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/Sirupsen/logrus:go_default_library",
            "//vendor/github.com/docker/docker/pkg/mount:go_default_library",
            "//vendor/github.com/docker/docker/pkg/symlink:go_default_library",
            "//vendor/github.com/golang/protobuf/proto:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/apparmor:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/cgroups:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/cgroups/fs:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/cgroups/systemd:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/configs/validate:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/criurpc:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/keys:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/label:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/seccomp:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/system:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/user:go_default_library",
            "//vendor/github.com/opencontainers/runc/libcontainer/utils:go_default_library",
            "//vendor/github.com/syndtr/gocapability/capability:go_default_library",
            "//vendor/github.com/vishvananda/netlink:go_default_library",
            "//vendor/github.com/vishvananda/netlink/nl:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/apparmor:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/cgroups:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/configs:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/criurpc:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/keys:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/label:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/seccomp:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/selinux:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/stacktrace:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/system:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/user:all-srcs",
        "//vendor/github.com/opencontainers/runc/libcontainer/utils:all-srcs",
    ],
    tags = ["automanaged"],
)
