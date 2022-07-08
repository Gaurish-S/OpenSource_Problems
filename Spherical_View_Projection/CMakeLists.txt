cmake_minimum_required(VERSION 3.2.1)
project (Spherical_View_Projection)

add_compile_options(-std=c++17)

find_package(PCL REQUIRED COMPONENTS)
find_package(OpenCV REQUIRED)

include_directories(include ${PCL_INCLUDE_DIRS}  ${OpenCV_INCLUDE_DIRS})

link_directories(${PCL_LIBRARY_DIRS})

add_definitions(${PCL_DEFINITIONS})

add_library(spherical_deps
    src/Spherical_View_Projection.cpp
)

# add_executable(spherical_node src/Spherical_View_Projection.cpp)

# target_link_libraries(spherical_node ${PCL_LIBRARIES} ${OpenCV_LIBS})
target_link_libraries(spherical_deps ${PCL_LIBRARIES} ${OpenCV_LIBS})


