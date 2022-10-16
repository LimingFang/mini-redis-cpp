cmake_minimum_required(VERSION 3.23)
project(mini-redis-cpp)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_subdirectory(thirdparty/folly)

add_library(mini_redis STATIC
  src/db.cc
  src/dict.cc
  src/redis.cc
  src/ae.cc
)

target_include_directories(mini_redis
  PUBLIC
  src
)
target_include_directories(mini_redis
  PUBLIC
  thirdparty/folly
)

list(APPEND THIRDPARTY_LIB
  folly
)

target_link_libraries(mini_redis
  ${THIRDPARTY_LIB}
)





