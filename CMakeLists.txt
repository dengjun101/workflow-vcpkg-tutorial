cmake_minimum_required(VERSION 3.12)

project(http_echo_server)

find_package(Workflow REQUIRED)
find_package(OpenSSL REQUIRED)

include_directories(${WORKFLOW_INCLUDE_DIR})
link_directories(${WORKFLOW_LIB_DIR})

add_executable(http_echo_server tutorial-04-http_echo_server.cc)

target_link_libraries(http_echo_server workflow ws2_32 Mswsock OpenSSL::Crypto OpenSSL::SSL) 
