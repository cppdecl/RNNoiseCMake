cmake_minimum_required(VERSION 3.30)

project(RNNoise)

set(CMAKE_C_STANDARD 11)

file(GLOB RNNOISE_SOURCES
        "Dependencies/RNNoise/src/*.c"
        "Dependencies/RNNoise/src/*.h"
        "Model/*.c"
        "Model/*.h"
)

add_library(${PROJECT_NAME} STATIC ${RNNOISE_SOURCES})

target_include_directories(${PROJECT_NAME} PUBLIC "Include")
target_compile_definitions(${PROJECT_NAME} PRIVATE _USE_MATH_DEFINES)

target_include_directories(${PROJECT_NAME} PUBLIC "Dependencies/RNNoise/src")
target_include_directories(${PROJECT_NAME} PUBLIC "Dependencies/RNNoise/include")
target_include_directories(${PROJECT_NAME} PUBLIC "Dependencies/RNNoise")
target_include_directories(${PROJECT_NAME} PUBLIC "Model")
