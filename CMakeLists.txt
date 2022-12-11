cmake_minimum_required(VERSION 3.16)

project(mimick_vendor)

find_package(ament_cmake REQUIRED)

include(FetchContent)

FetchContent_Declare(
  mimick
  GIT_REPOSITORY https://github.com/ros2/Mimick.git
  GIT_TAG        de11f8377eb95f932a03707b583bf3d4ce5bd3e7
)

FetchContent_MakeAvailable(mimick)

ament_export_include_directories(include)
ament_export_libraries(mimick)
ament_export_dependencies(mimick)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

# this ensures that the package has an environment hook setting the PATH
ament_package()
