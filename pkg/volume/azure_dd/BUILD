package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = [
        "attacher.go",
        "azure_common.go",
        "azure_common_linux.go",
        "azure_common_unsupported.go",
        "azure_common_windows.go",
        "azure_dd.go",
        "azure_dd_block.go",
        "azure_mounter.go",
        "azure_provision.go",
    ],
    importpath = "k8s.io/kubernetes/pkg/volume/azure_dd",
    deps = [
        "//pkg/apis/core:go_default_library",
        "//pkg/cloudprovider:go_default_library",
        "//pkg/cloudprovider/providers/azure:go_default_library",
        "//pkg/features:go_default_library",
        "//pkg/util/keymutex:go_default_library",
        "//pkg/util/mount:go_default_library",
        "//pkg/util/strings:go_default_library",
        "//pkg/volume:go_default_library",
        "//pkg/volume/util:go_default_library",
        "//pkg/volume/util/volumepathhandler:go_default_library",
        "//staging/src/k8s.io/api/core/v1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/api/resource:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/types:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/sets:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/wait:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/util/feature:go_default_library",
        "//vendor/github.com/Azure/azure-sdk-for-go/services/compute/mgmt/2017-12-01/compute:go_default_library",
        "//vendor/github.com/Azure/azure-sdk-for-go/services/storage/mgmt/2017-10-01/storage:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
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

go_test(
    name = "go_default_test",
    srcs = [
        "azure_common_test.go",
        "azure_dd_block_test.go",
        "azure_dd_test.go",
    ],
    embed = [":go_default_library"],
    deps = [
        "//pkg/util/mount:go_default_library",
        "//pkg/volume:go_default_library",
        "//pkg/volume/testing:go_default_library",
        "//staging/src/k8s.io/api/core/v1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/types:go_default_library",
        "//staging/src/k8s.io/client-go/util/testing:go_default_library",
    ],
)
