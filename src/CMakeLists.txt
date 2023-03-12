set(HEADER_LIST "${PROJECT_SOURCE_DIR}/include/cmake_tests/hello.h")

# Make an automatic library - will be static or dynamic based on user setting
add_library(cmake_tests_library hello.c ${HEADER_LIST})

# We need this directory, and users of our library will need it too
target_include_directories(cmake_tests_library PUBLIC ../include)

# This depends on (header only) boost
target_link_libraries(cmake_tests_library PRIVATE greetings)

# IDEs should put the headers in a nice place
source_group(
  TREE "${PROJECT_SOURCE_DIR}/include"
  PREFIX "Header Files"
  FILES ${HEADER_LIST})
