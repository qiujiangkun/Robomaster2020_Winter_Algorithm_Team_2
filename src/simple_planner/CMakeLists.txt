cmake_minimum_required(VERSION 3.1)
project(simple_planner)

set(CMAKE_CXX_STANDARD 11)

#############################
#Dependencies
#############################

find_package(Eigen3 REQUIRED)
find_package(catkin REQUIRED COMPONENTS
    roscpp
    tf
    nav_msgs
    geometry_msgs
)
catkin_package()

include_directories(${catkin_INCLUDE_DIRS} ${EIGEN3_INCLUDE_DIR})


add_executable(global_path_specifier global_path_specifier.cpp)
target_link_libraries(global_path_specifier ${catkin_LIBRARIES})

add_executable(global_planner global_planner.cpp)
target_link_libraries(global_planner ${catkin_LIBRARIES})

add_executable(my_planner my_planner.cpp)
target_link_libraries(my_planner ${catkin_LIBRARIES})

add_executable(local_planner local_planner.cpp)
target_link_libraries(local_planner ${catkin_LIBRARIES})

add_executable(pid_planner pid_planner.cpp)
target_link_libraries(pid_planner ${catkin_LIBRARIES})

