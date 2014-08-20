cmake_minimum_required(VERSION 2.8.3)
project(armadillo_matrix)

find_package(catkin REQUIRED COMPONENTS roscpp)

################################################
#                                              #
#       CATKIN SPECIFIC CONFIGURATION          #
#                                              #
################################################

catkin_package(
    LIBRARIES armadillo
    INCLUDE_DIRS include
)

################################################
#                                              #
#                    BUILD                     #
#                                              #
################################################

include_directories(include)

add_library(armadillo src/wrap_libs.cpp)

