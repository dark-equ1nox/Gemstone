cmake_minimum_required(VERSION 4.3)
project(Gemstone)

set(CMAKE_CXX_STANDARD 20)

add_executable(Gemstone main.cpp)

find_package(slang CONFIG HINTS "$ENV{VULKAN_SDK}/lib/cmake")

list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/CMake")

#find_package (Vulkan REQUIRED)

## set up Vulkan C++ module (enabled when ENABLE_CPP20_MODULE=ON)
#add_library(VulkanCppModule)
#add_library(Vulkan::cppm ALIAS VulkanCppModule)
#
#target_compile_definitions(VulkanCppModule PUBLIC
#        VULKAN_HPP_DISPATCH_LOADER_DYNAMIC=1
#        VULKAN_HPP_NO_STRUCT_CONSTRUCTORS=1
#)
#
#target_include_directories(VulkanCppModule PRIVATE "${Vulkan_INCLUDE_DIR}")
#
#target_link_libraries(VulkanCppModule PUBLIC Vulkan::Vulkan)
#
#set_target_properties(VulkanCppModule PROPERTIES CXX_STANDARD 20)
#
#target_sources(VulkanCppModule
#        PUBLIC
#        FILE_SET cxx_modules TYPE CXX_MODULES
#        BASE_DIRS "${Vulkan_INCLUDE_DIR}"
#        FILES "${Vulkan_INCLUDE_DIR}/vulkan/vulkan.cppm"
#)
#
#target_link_libraries (${PROJECT_NAME} Vulkan::cppm)