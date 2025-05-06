java_toolchain(
    name = "fleetman_api_gateway_toolchain",
    source_version = "17",
    target_version = "17",
)

java_binary(
    name = "fleetman-api-gateway",
    srcs = ["src/main/java/com/virtualpairprogrammers/api/FleetmanApiGateway.java"],
    main_class = "com.virtualpairprogrammers.api.FleetmanApiGateway",
    deps = [":fleetman_lib"],
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
)

java_test(
    name = "fleetman_tests",
    srcs = glob(["src/test/java/com/virtualpairprogrammers/**/*.java"]),
    deps = [
        ":fleetman_lib",
        "@maven//:org_springframework_boot_spring_boot_starter_test",
        "@maven//:junit_junit",
    ],
)