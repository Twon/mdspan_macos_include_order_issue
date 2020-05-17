cmake_minimum_required(VERSION 3.14)

project(client_server_example)

include(FetchContent)
FetchContent_Declare(mdspan GIT_REPOSITORY https://github.com/kokkos/mdspan.git)
FetchContent_MakeAvailable(mdspan)

add_executable(mdspan_test main.cpp)
target_link_libraries(mdspan_test
    PRIVATE
        std::mdspan
)

set_target_properties(mdspan_test PROPERTIES
    CXX_STANDARD 20
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)