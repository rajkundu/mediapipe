# Copyright 2023 The MediaPipe Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

package(default_visibility = ["//mediapipe/tasks:internal"])

licenses(["notice"])

objc_library(
    name = "MPPObjectDetectionResult",
    srcs = ["sources/MPPObjectDetectionResult.m"],
    hdrs = ["sources/MPPObjectDetectionResult.h"],
    deps = [
        "//mediapipe/tasks/ios/components/containers:MPPDetection",
        "//mediapipe/tasks/ios/core:MPPTaskResult",
    ],
)

objc_library(
    name = "MPPObjectDetectorOptions",
    srcs = ["sources/MPPObjectDetectorOptions.m"],
    hdrs = ["sources/MPPObjectDetectorOptions.h"],
    deps = [
        ":MPPObjectDetectionResult",
        "//mediapipe/tasks/ios/core:MPPTaskOptions",
        "//mediapipe/tasks/ios/vision/core:MPPRunningMode",
    ],
)

objc_library(
    name = "MPPObjectDetector",
    srcs = ["sources/MPPObjectDetector.mm"],
    hdrs = ["sources/MPPObjectDetector.h"],
    copts = [
        "-ObjC++",
        "-std=c++17",
        "-x objective-c++",
    ],
    deps = [
        ":MPPObjectDetectionResult",
        ":MPPObjectDetectorOptions",
        "//mediapipe/tasks/cc/vision/object_detector:object_detector_graph",
        "//mediapipe/tasks/ios/common/utils:MPPCommonUtils",
        "//mediapipe/tasks/ios/common/utils:NSStringHelpers",
        "//mediapipe/tasks/ios/core:MPPTaskInfo",
        "//mediapipe/tasks/ios/vision/core:MPPImage",
        "//mediapipe/tasks/ios/vision/core:MPPVisionPacketCreator",
        "//mediapipe/tasks/ios/vision/core:MPPVisionTaskRunner",
        "//mediapipe/tasks/ios/vision/object_detector/utils:MPPObjectDetectionResultHelpers",
        "//mediapipe/tasks/ios/vision/object_detector/utils:MPPObjectDetectorOptionsHelpers",
        "//third_party/apple_frameworks:UIKit",
    ],
)
