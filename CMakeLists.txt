cmake_minimum_required(VERSION 3.0)
project(SouthTiger)

find_package(OpenCV REQUIRED)

set(PROTO_AD_DIR ${PROJECT_SOURCE_DIR}/ArmorDescriptor/include)
set(PROTO_AP_DIR ${PROJECT_SOURCE_DIR}/ArmorParam/include)
set(PROTO_LD_DIR ${PROJECT_SOURCE_DIR}/LightDescriptor/include)


add_subdirectory(ArmorDescriptor)
add_subdirectory(ArmorParam)
add_subdirectory(LightDescriptor)
include_directories(${PROJECT_SOURCE_DIR}
    ${PROTO_AD_DIR} ${PROTO_AP_DIR} ${PROTO_LD_DIR}
)

add_executable(${PROJECT_NAME} main.cpp )

TARGET_LINK_LIBRARIES(SouthTiger ${OpenCV_LIBS})
