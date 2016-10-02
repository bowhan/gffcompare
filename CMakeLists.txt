cmake_minimum_required(VERSION 3.0)

include_directories(gclib)
add_subdirectory(gclib)


set(GFFCOMPARE_SOURCE_FILES
        gffcompare.cpp
        gtf_tracking.cpp)

OPTION(BUILD_STATIC "build staticly linked binraries" OFF)
if (BUILD_STATIC)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -static")
    set(GCLIB gclib_static)
else ()
    set(CMAKE_BUILD_WITH_INSTALL_RPATH FALSE)
    set(CMAKE_INSTALL_RPATH "${CMAKE_INSTALL_PREFIX}/lib")
    set(GCLIB gclib)
endif ()

add_executable(gffcompare gffcompare.cpp ${GFFCOMPARE_SOURCE_FILES})
target_link_libraries(gffcompare ${GCLIB})

install(TARGETS gffcompare
        RUNTIME DESTINATION bin)