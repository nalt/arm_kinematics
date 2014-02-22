cmake_minimum_required(VERSION 2.8.3)
project(arm_kinematics)

find_package(catkin REQUIRED COMPONENTS roscpp tf sensor_msgs urdf kdl_parser tf_conversions)

find_package(Eigen REQUIRED)
find_package(orocos_kdl REQUIRED)

include_directories(${Eigen_INCLUDE_DIRS})

catkin_package(
    #INCLUDE_DIRS include
    #LIBRARIES ${PROJECT_NAME}
    #CATKIN_DEPENDS roscpp
    #DEPENDS Eigen OpenCV Bullet
)

add_executable(arm_kinematics arm_kinematics.cpp)
target_link_libraries(arm_kinematics ${catkin_LIBRARIES} ${orocos_kdl_LIBRARIES})
