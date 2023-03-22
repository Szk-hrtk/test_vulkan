cmake_minimum_required(VERSION 3.24)
project(Vulkan_test_1)

set(CMAKE_CXX_STANDARD 17 -wall)
set(CMAKE_CXX_FLAGS_DEBUG "-O0 -g3 -pg")
set(CMAKE_CXX_FLAGS_RELEASE "-O2 -s -DNDEBUG -march=native")

set(glm_DIR C:/glm-0.9.9.8/glm/cmake/glm)
find_package(glm REQUIRED)
find_package(Vulkan REQUIRED)
find_package(glfw3 REQUIRED)

add_executable(Vulkan_test_1 main.cpp)

target_include_directories(
        ${PROJECT_NAME}
        PUBLIC ${Vulkan_INCLUDE_DIR}
        glfw
)

target_link_libraries(
        ${PROJECT_NAME}
        ${Vulkan_LIBRARIES}
        glfw
        glm::glm
)

