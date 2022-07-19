cmake_minimum_required(VERSION 3.12)

message(STATUS "VCPKG_DIR: $ENV{VCPKG_DIR}")
if(DEFINED ENV{VCPKG_DIR} AND NOT DEFINED CMAKE_TOOLCHAIN_FILE)
	set(CMAKE_TOOLCHAIN_FILE $ENV{VCPKG_DIR}/scripts/buildsystems/vcpkg.cmake CACHE STRING "")
endif()
message(STATUS "CMAKE_TOOLCHAIN_FILE: ${CMAKE_TOOLCHAIN_FILE}")
#include(c:/work/code/vcpkg/scripts/buildsystems/vcpkg.cmake)
project(rabbitmq_test)

add_executable(01_send "01/01_send.cpp")
target_link_libraries(01_send SimpleAmqpClient.7)
set_target_properties(01_send PROPERTIES CXX_STANDARD 17)

add_executable(01_receive "01/01_receive.cpp")
target_link_libraries(01_receive SimpleAmqpClient.7)
set_target_properties(01_receive PROPERTIES CXX_STANDARD 17)

add_executable(02_send "02/02_send.cpp")
target_link_libraries(02_send SimpleAmqpClient.7)
set_target_properties(02_send PROPERTIES CXX_STANDARD 17)

add_executable(02_receive "02/02_receive.cpp")
target_link_libraries(02_receive SimpleAmqpClient.7)
set_target_properties(02_receive PROPERTIES CXX_STANDARD 17)

add_executable(03_send "03/03_send.cpp")
target_link_libraries(03_send SimpleAmqpClient.7)
set_target_properties(03_send PROPERTIES CXX_STANDARD 17)

add_executable(03_receive "03/03_receive.cpp")
target_link_libraries(03_receive SimpleAmqpClient.7)
set_target_properties(03_receive PROPERTIES CXX_STANDARD 17)

add_executable(04_send "04/04_send.cpp")
target_link_libraries(04_send SimpleAmqpClient.7)
set_target_properties(04_send PROPERTIES CXX_STANDARD 17)

add_executable(04_receive "04/04_receive.cpp")
target_link_libraries(04_receive SimpleAmqpClient.7)
set_target_properties(04_receive PROPERTIES CXX_STANDARD 17)

add_executable(05_send "05/05_send.cpp")
target_link_libraries(05_send SimpleAmqpClient.7)
set_target_properties(05_send PROPERTIES CXX_STANDARD 17)

add_executable(05_receive "05/05_receive.cpp")
target_link_libraries(05_receive SimpleAmqpClient.7)
set_target_properties(05_receive PROPERTIES CXX_STANDARD 17)

add_executable(rpc_client "06/rpc_client.cpp")
target_link_libraries(rpc_client SimpleAmqpClient.7)
set_target_properties(rpc_client PROPERTIES CXX_STANDARD 17)
target_compile_definitions(rpc_client PRIVATE _HAS_AUTO_PTR_ETC)

add_executable(rpc_server "06/rpc_server.cpp")
target_link_libraries(rpc_server SimpleAmqpClient.7)
set_target_properties(rpc_server PROPERTIES CXX_STANDARD 17)
target_compile_definitions(rpc_server PRIVATE _HAS_AUTO_PTR_ETC)
