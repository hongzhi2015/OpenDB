add_library(zutil
    misc_functions.cpp
    atypes.cpp files.cpp
    name.cpp
    mem.cpp
    parse.cpp
    graph.cpp
    kdtree.cpp
    gz.cpp
    debug_filter.cpp
    poly_decomp.cpp
    b100.cpp xf.cpp
    dgraph.cpp
    charBuffer.cpp
)

target_include_directories(zutil
    PUBLIC
        $<INSTALL_INTERFACE:include/opendb>
        $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include/opendb>
    PRIVATE
        ${PROJECT_SOURCE_DIR}/src/zutil
)

target_compile_features(zutil PRIVATE cxx_auto_type)
target_compile_options(zutil PRIVATE $<$<CXX_COMPILER_ID:GNU>:-Wall>)
set_property(TARGET zutil PROPERTY POSITION_INDEPENDENT_CODE ON)