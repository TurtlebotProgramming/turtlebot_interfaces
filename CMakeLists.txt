cmake_minimum_required(VERSION 3.8)
project(turtlebot_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/TurtlebotImu.msg"
  "msg/Ui2Taskplanner.msg"
  "msg/Refiner2taskplanner.msg"
  "action/Gripper.action"
  DEPENDENCIES std_msgs geometry_msgs
)

ament_export_dependencies(std_msgs geometry_msgs rosidl_default_generators)
ament_package()
