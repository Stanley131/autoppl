# Configure test coverage
if (AUTOPPL_ENABLE_TEST_COVERAGE)
    message(STATUS "Building test suite with coverage information")
    add_compile_options(--coverage -O0 -fno-inline -fno-inline-small-functions
                        -fno-default-inline)
endif()

######################################################
# Dummy Test
######################################################

add_executable(dummy_unittest
    test1.cpp
    )
target_compile_options(dummy_unittest PRIVATE -g -Wall -Werror -Wextra)
target_include_directories(dummy_unittest PRIVATE ${GTEST_DIR}/include)
if (AUTOPPL_ENABLE_TEST_COVERAGE)
    target_link_libraries(dummy_unittest gcov)
endif()
target_link_libraries(dummy_unittest gtest_main pthread ${PROJECT_NAME})
add_test(dummy_unittest dummy_unittest)
