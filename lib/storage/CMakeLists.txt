cmake_minimum_required(VERSION 3.5)
project(Storage)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(Storage_dir             storage)

#****************************************************************************************************
set(STORAGE_SRC
     database.h
     database.cpp
)

#****************************************************************************************************

add_library(${STORAGE_LIB_NAME} ${STORAGE_SRC})
target_include_directories(${STORAGE_LIB_NAME} PUBLIC .)

#****************************************************************************************************
find_package(SQLite3 REQUIRED)

target_link_libraries (${STORAGE_LIB_NAME} ${SQLite3_LIBRARIES} ${PROTOCOL_LIB_NAME})
