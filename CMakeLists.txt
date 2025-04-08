cmake_minimum_required( VERSION 3.25 FATAL_ERROR )

project( gfxsamples
    C CXX
)

# cmake modules folder
list( APPEND CMAKE_MODULE_PATH
    "${CMAKE_CURRENT_LIST_DIR}/cmake_modules"
)

# C++ options
set( CMAKE_CXX_STANDARD 20 )
set( CMAKE_CXX_STANDARD_REQUIRED ON )
set( CMAKE_CXX_EXTENSIONS OFF )

# force to release build if nothing else is defined
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Force to set Release build" FORCE)
endif()
add_compile_definitions(
    $<IF:$<CONFIG:DEBUG>,_DEBUG,NDEBUG>
)

# set MSVC warning C4996 to "off"
add_definitions(-D_CRT_SECURE_NO_WARNINGS)

# place all artifacts into one folder
# NOTE: this is fine for the education,
# however this is bad practice for the real project
set( CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/bin" )

# list of samples to build
set( SUPPORT_VULKAN false )
set( SUPPORT_OPENGL false )
set( SUPPORT_DIRECT3D false )

# detect the support from the operation system
if( LINUX )
    set( SUPPORT_VULKAN true )
    set( SUPPORT_OPENGL true )
endif()
if( WIN32 )
    set( SUPPORT_VULKAN true )
    set( SUPPORT_OPENGL true )
    set( SUPPORT_DIRECT3D true )
endif()
