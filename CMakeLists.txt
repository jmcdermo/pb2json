CMAKE_MINIMUM_REQUIRED(VERSION 3.8)
project(pb2json)

add_library(pb2json_lib_static STATIC pb2json.cpp pb2json.h)

target_include_directories(pb2json_lib_static PRIVATE ${Protobuf_INCLUDES})
target_include_directories(pb2json_lib_static PRIVATE ${jansson_BINARY_DIR}/include)

target_link_libraries(pb2json_lib_static PRIVATE jansson)
target_link_libraries(pb2json_lib_static PRIVATE ${Protobuf_LIBRARY})
