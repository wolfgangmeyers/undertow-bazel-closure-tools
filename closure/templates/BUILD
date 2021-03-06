# Copyright 2016 The Bazel Authors. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

package(default_visibility = ["//visibility:public"])

load("//closure/compiler:closure_js_library.bzl", "closure_js_library")

java_library(
    name = "templates",
    exports = ["@soy//jar"],
    runtime_deps = [
        "@aopalliance//jar",
        "@asm//jar",
        "@asm_analysis//jar",
        "@asm_commons//jar",
        "@asm_util//jar",
        "@bazel_tools//third_party:guava",
        "@bazel_tools//third_party:jsr305",
        "@bazel_tools//third_party:jsr330_inject",
        "@guice//jar",
        "@guice_assistedinject//jar",
        "@guice_multibindings//jar",
        "@icu4j//jar",
    ],
)

closure_js_library(
    name = "soyutils_usegoog",
    srcs = ["@soyutils_usegoog//file"],
    deps = ["//closure/library"],
)

java_binary(
    name = "SoyParseInfoGenerator",
    jvm_flags = ["-client"],
    main_class = "com.google.template.soy.SoyParseInfoGenerator",
    runtime_deps = [
        "@args4j//jar",
        ":templates",
    ],
)

java_binary(
    name = "SoyToJsSrcCompiler",
    jvm_flags = ["-client"],
    main_class = "com.google.template.soy.SoyToJsSrcCompiler",
    runtime_deps = [
        "@args4j//jar",
        ":templates",
    ],
)
