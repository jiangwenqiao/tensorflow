load("@build_bazel_rules_android//android:rules.bzl", "android_binary")

# Sample app for OVIC benchmarking.
licenses(["notice"])  # Apache 2.0

android_binary(
    name = "ovic_benchmarker_binary",
    srcs = [
        "OvicBenchmarkerActivity.java",
    ],
    aapt_version = "aapt",
    assets = [
        "//tensorflow/contrib/lite/java/ovic/src/testdata:coco_labels.txt",
        "//tensorflow/contrib/lite/java/ovic/src/testdata:labels.txt",
        "//tensorflow/contrib/lite/java/ovic/src/testdata:ovic_testdata",
        "@tflite_mobilenet_ssd_quant//:detect.tflite",
    ],
    assets_dir = "",
    custom_package = "ovic.demo.app",
    manifest = "AndroidManifest.xml",
    nocompress_extensions = [
        ".lite",
        ".tflite",
    ],
    resource_files = glob(["res/**"]),
    tags = ["manual"],
    deps = [
        "//tensorflow/contrib/lite/java:tensorflowlite",
        "//tensorflow/contrib/lite/java/ovic:ovicbenchmarkerlib",
        "//tensorflow/contrib/lite/java/ovic:ovicdetectionbenchmarkerlib",
        "@androidsdk//com.android.support:support-v13-25.2.0",
        "@androidsdk//com.android.support:support-v4-25.2.0",
    ],
)
