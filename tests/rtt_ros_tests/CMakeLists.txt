cmake_minimum_required(VERSION 2.8.3)
project(rtt_ros_tests)

find_package(catkin REQUIRED COMPONENTS rtt_ros)

if(CATKIN_ENABLE_TESTING)

  orocos_use_package(ocl-logging)
  orocos_use_package(ocl-deployment)

  catkin_add_gtest(rtt_ros_api_tests test/api_tests.cpp)
  target_link_libraries(rtt_ros_api_tests
    ${catkin_LIBRARIES}
    ${USE_OROCOS_LIBRARIES}
    ${OROCOS-RTT_LIBRARIES}
    ${OROCOS-RTT_RTT-SCRIPTING_LIBRARY})

  orocos_generate_package()

endif()
