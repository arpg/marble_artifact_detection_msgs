cmake_minimum_required(VERSION 2.8.3)
project(marble_artifact_detection_msgs)
set(CMAKE_CXX_STANDARD 11)

list(APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake_modules/")

find_package(catkin REQUIRED
  COMPONENTS
    roscpp
    std_msgs
    geometry_msgs
    sensor_msgs
    message_generation
    tf
)

add_definitions(${EIGEN_DEFINITIONS})

add_message_files(
  DIRECTORY
    msg
  FILES
    Artifact.msg
    ArtifactArray.msg
    ArtifactMap.msg
    ArtifactView.msg
    ArtifactImg.msg
  )

generate_messages(
  DEPENDENCIES
    roscpp
    std_msgs
    geometry_msgs
    sensor_msgs
)

catkin_package(
  CATKIN_DEPENDS roscpp std_msgs geometry_msgs sensor_msgs message_runtime
  )

include_directories(
    ${catkin_INCLUDE_DIRS}
    )
