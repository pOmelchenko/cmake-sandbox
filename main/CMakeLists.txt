add_executable(cmake_tests src/main.c)

target_link_libraries(cmake_tests PRIVATE say-hello)
