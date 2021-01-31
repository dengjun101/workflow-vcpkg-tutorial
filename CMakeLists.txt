cmake_minimum_required(VERSION 3.12)

project(http_echo_server)

find_package(Workflow REQUIRED)
find_package(OpenSSL REQUIRED)


add_executable(http_echo_server tutorial-04-http_echo_server.cc)

target_link_libraries(http_echo_server Workflow::workflow OpenSSL::Crypto OpenSSL::SSL) 
