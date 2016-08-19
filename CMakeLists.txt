cmake_minimum_required(VERSION 3.2.0)
project(cmake-xcode-multiplatform)

# Enable Apple-specific platforms on Xcode
if(CMAKE_GENERATOR STREQUAL Xcode)
    set(CMAKE_XCODE_ATTRIBUTE_SUPPORTED_PLATFORMS "macosx iphoneos iphonesimulator")
    set(CMAKE_XCODE_EFFECTIVE_PLATFORMS "-macosx;-iphoneos;-iphonesimulator")

    set(CMAKE_MACOSX_BUNDLE true)
endif()

add_library(library library.cpp)

add_executable(main main.cpp)
target_link_libraries(main library)
