cmake_minimum_required(VERSION 3.25.0)
project(cmake_tests VERSION 0.1.0 LANGUAGES C)

set(CMAKE_GENERATOR Ninja)

set(SOME_VAR "THIS IS FORM VAR")
message(STATUS "Hello from CMakeLists.txt | ${SOME_VAR} | ${PROJECT_VERSION}")

set(my_bool FALSE)

if(NOT my_bool)
    message(STATUS "!!! Cond was met")
else()
    message(STATUS "!!! Cond failed")
endif()

set(my_value 4)
while(my_value LESS 20)
    message(STATUS "!!! my value ${my_value}")
    math(EXPR my_value "${my_value} + 2")
endwhile()

message(STATUS "!!! foreach(item IN ITEMS foo bar baz)")

foreach(item IN ITEMS foo bar baz)
    message(STATUS "!!! ${item}")
endforeach()

message(STATUS "!!! foreach(idx RANGE 10)")

foreach(idx RANGE 10)
    message(STATUS "!!! ${idx}")
endforeach()

message(STATUS "!!! foreach(idx RANGE 10 20)")

foreach(idx RANGE 10 20)
    message(STATUS "!!! ${idx}")
endforeach()

message(STATUS "!!! foreach(idx RANGE 10 20 2)")

foreach(idx RANGE 10 20 2)
    message(STATUS "!!! ${idx}")
endforeach()


# include(CTest)
# enable_testing()

add_subdirectory(say-hello)
add_subdirectory(main)

# set(CPACK_PROJECT_NAME ${PROJECT_NAME})
# set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})

# include(CPack)
