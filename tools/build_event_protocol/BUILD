load("@build_bazel_rules_typescript//:defs.bzl", "ts_library", "ts_proto_library")
load("@build_bazel_rules_nodejs//:defs.bzl", "nodejs_binary")

ts_proto_library(
    name = "build_event_stream",
    deps = ["//third_party/github.com/bazelbuild/bazel/src/main/java/com/google/devtools/build/lib/buildeventstream/proto"],
)

ts_library(
    name = "parse_bep",
    srcs = ["parse_bep.ts"],
    deps = [
      ":build_event_stream",
    ],
)

nodejs_binary(
    name = "parse",
    entry_point = "angular_devkit/tools/build_event_protocol/parse_bep",
    data = [":parse_bep"],
)
