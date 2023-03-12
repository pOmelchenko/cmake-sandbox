add_executable(greetings greetings.c)

target_link_libraries(greetings PRIVATE cmake_tests_library)
