cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

project("jsonld-cpp-client" VERSION 0.5.0
        LANGUAGES CXX )

find_package(jsonld-cpp 0.5.0 CONFIG REQUIRED)



add_executable(expand-jsonld expand-jsonld.cpp)

target_compile_features(expand-jsonld PRIVATE cxx_std_14)
set_target_properties(expand-jsonld PROPERTIES CXX_EXTENSIONS OFF)

target_link_libraries(expand-jsonld jsonld-cpp::jsonld-cpp)


add_executable(jsonld2rdf jsonld2rdf.cpp)

target_compile_features(jsonld2rdf PRIVATE cxx_std_14)
set_target_properties(jsonld2rdf PROPERTIES CXX_EXTENSIONS OFF)

target_link_libraries(jsonld2rdf jsonld-cpp::jsonld-cpp)
