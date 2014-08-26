cmake_minimum_required(VERSION 2.8.3)
project(armadillo_matrix)
find_package(catkin REQUIRED)

################################################
#                                              #
#       CATKIN SPECIFIC CONFIGURATION          #
#                                              #
################################################

find_package(LAPACK REQUIRED)
find_package(BLAS REQUIRED)

message("LAPACK_LIBRARIES" ${LAPACK_LIBRARIES})
message("BLAS_LIBRARIES" ${BLAS_LIBRARIES})

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES armadillo
  DEPENDS LAPACK BLAS
)

################################################
#                                              #
#                    BUILD                     #
#                                              #
################################################

include_directories(include)

add_library(armadillo src/wrap_libs.cpp)
target_link_libraries(armadillo
  ${LAPACK_LIBRARIES}
  ${BLAS_LIBRARIES}
)
