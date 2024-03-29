cmake_minimum_required(VERSION 3.5)
project(tachimawari_interfaces)

if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/ControlJoints.msg"
  "msg/CurrentJoints.msg"
  "msg/Joint.msg"
  "msg/Packet.msg"
  "msg/SetJoints.msg"
  "msg/SetTorques.msg"
  "msg/Status.msg")

ament_export_dependencies(rosidl_default_runtime)
ament_package()
