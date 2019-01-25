cmake_minimum_required(VERSION 2.8)

project(helloworld)
add_executable(helloworld hello.c)

find_package (BZip2)
if (BZIP2_FOUND)
  message("Found BZIP2")
  include_directories(${BZIP_INCLUDE_DIRS})
  target_link_libraries (helloworld ${BZIP2_LIBRARIES})
else(BZIP2_FOUND)
  message("BZIP2 not found")
endif (BZIP2_FOUND)
