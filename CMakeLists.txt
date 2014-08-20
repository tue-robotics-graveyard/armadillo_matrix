cmake_minimum_required(VERSION 2.8.3)
project(armadillo_matrix)
find_package(catkin REQUIRED)

################################################
#                                              #
#       CATKIN SPECIFIC CONFIGURATION          #
#                                              #
################################################

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES armadillo
  DEPENDS lapack blas
)

################################################
#                                              #
#                    BUILD                     #
#                                              #
################################################

include_directories(include)

add_library(armadillo src/wrap_libs.cpp)
target_link_libraries(armadillo lapack blas)
