cmake_minimum_required(VERSION 3.22)

project(Server)

include(ExternalProject)

ExternalProject_Add(ChatServer
    SOURCE_DIR ${CMAKE_SOURCE_DIR}/ChatServer
    BINARY_DIR ${CMAKE_SOURCE_DIR}/ChatServer/build
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=${CMAKE_SOURCE_DIR}/ChatServer/build
)

ExternalProject_Add(ChatServer2
    SOURCE_DIR ${CMAKE_SOURCE_DIR}/ChatServer2
    BINARY_DIR ${CMAKE_SOURCE_DIR}/ChatServer2/build
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=${CMAKE_SOURCE_DIR}/ChatServer2/build
)

ExternalProject_Add(GateServer
    SOURCE_DIR ${CMAKE_SOURCE_DIR}/GateServer
    BINARY_DIR ${CMAKE_SOURCE_DIR}/GateServer/build
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=${CMAKE_SOURCE_DIR}/GateServer/build
)

ExternalProject_Add(StatusServer
    SOURCE_DIR ${CMAKE_SOURCE_DIR}/StatusServer
    BINARY_DIR ${CMAKE_SOURCE_DIR}/StatusServer/build
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=${CMAKE_SOURCE_DIR}/StatusServer/build
)
