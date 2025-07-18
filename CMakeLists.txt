cmake_minimum_required(VERSION 3.25.0)
set(PROJECT_NAME TsfApp)
project(${PROJECT_NAME} LANGUAGES CXX C)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_definitions(
    /D_UNICODE=1
    /DUNICODE=1
)

# fmt
find_package(fmt CONFIG REQUIRED)

include_directories("./")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

set(MY_EXECUTABLE_NAME "TsfApp")

add_executable(${PROJECT_NAME} WIN32
    "./afxres.h"
    "./context.cpp"
    "./dataobj.cpp"
    "./dataobj.h"
    "./funcprov.cpp"
    "./globals.h"
    "./persist.cpp"
    "./propldr.cpp"
    "./propldr.h"
    "./resource.h"
    "./test.cpp"
    "./textstor.cpp"
    "./tsfapp.cpp"
    "./tsfapp.rc"
    "./tsfedit.cpp"
    "./tsfedit.h"
    "./tsfwnd.cpp"
    "./tsfwnd.h"
    "./winres.h"
)

target_link_libraries(${PROJECT_NAME} PUBLIC 
    comctl32.lib
    fmt::fmt-header-only
)