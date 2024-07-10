include(FetchContent)

FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        release-1.12.1
)
FetchContent_MakeAvailable(googletest)

add_executable(uvco_test
    uvco_type_test.cc
    )

target_include_directories(uvco_test PRIVATE
    ${CppcoroIncludeDir}
    )

target_link_libraries(uvco_test PRIVATE
    gtest_main
    uvco
    )

include(GoogleTest)
gtest_discover_tests(uvco_test)
