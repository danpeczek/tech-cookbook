project(chapters)

set(HEADERS
    include/chapters/chapter1.hpp
    include/chapters/chapter2.hpp
    include/chapters/chapter3.hpp
    include/chapters/chapter4.hpp
    include/chapters/chapter5.hpp
    include/chapters/chapter6.hpp
    include/chapters/chapter7.hpp
    include/chapters/chapter8.hpp
    include/chapters/chapter9.hpp
    include/chapters/chapter10.hpp
    include/chapters/chapter11.hpp
    include/chapters/chapter12.hpp
    include/chapters/chapter13.hpp
    include/chapters/chapter14.hpp
    include/chapters/chapter15.hpp
)

set(SOURCES
    src/chapter1.cpp
    src/chapter2.cpp
    src/chapter3.cpp
    src/chapter4.cpp
    src/chapter5.cpp
    src/chapter6.cpp
    src/chapter7.cpp
    src/chapter8.cpp
    src/chapter9.cpp
    src/chapter10.cpp
    src/chapter11.cpp
    src/chapter12.cpp
    src/chapter13.cpp
    src/chapter14.cpp
    src/chapter15.cpp
)

add_library(${PROJECT_NAME}
    STATIC
    ${HEADERS}
    ${SOURCES}
)

target_link_libraries(${PROJECT_NAME}
  PUBLIC
  basics
  common
  details
)


target_include_directories(${PROJECT_NAME}
    PUBLIC
    ${CMAKE_CURRENT_LIST_DIR}/include
    ${CMAKE_CURRENT_SOURCE_DIR}
)

target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_17)
target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra -pedantic)
if (UNIX)
  target_compile_options(${PROJECT_NAME} PRIVATE -Wextra)
endif(UNIX)
