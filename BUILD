java_runtime(
    name = "local_jdk_runtime",
    java_home = "/usr/lib/jvm/java-17-openjdk-amd64",
    visibility = ["//visibility:public"],
)

java_toolchain(
    name = "java17_toolchain",
    source_version = "17",
    target_version = "17",
    java_runtime = ":local_jdk_runtime",
)


java_binary(
    name = "fleetman-api-gateway",
    srcs = ["src/main/java/com/virtualpairprogrammers/api/FleetmanApiGateway.java"],
    main_class = "com.virtualpairprogrammers.api.FleetmanApiGateway",
    deps = [":fleetman_lib"],
    toolchains = [":java17_toolchain"],
)

java_library(
    name = "fleetman_lib",
    srcs = glob(["src/main/java/com/virtualpairprogrammers/**/*.java"]),
    deps = [
        "@maven//:org_springframework_boot_spring_boot_starter_web",
        "@maven//:org_springframework_cloud_spring_cloud_starter_openfeign",
        "@maven//:javax_xml_bind_jaxb_api",
    ],
    resources = glob(["src/main/resources/**"]),
    toolchains = [":java17_toolchain"],
)