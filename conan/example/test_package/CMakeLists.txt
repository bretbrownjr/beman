cmake_minimum_required(VERSION 3.23)
project(example-package-test
  LANGUAGES CXX
  DESCRIPTION "Demonstrates usage of the example library."
)
include(CTest)

if(BUILD_TESTING)
  find_package(example REQUIRED)

  add_executable(example)
  target_sources(example PRIVATE test/example-example.cpp)
  target_link_libraries(example PRIVATE example::example)
endif()
