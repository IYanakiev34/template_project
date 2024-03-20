if(BUILD_TESTING)
  message(STATUS "Testing is on")
endif()

add_executable(main main.cpp)
target_link_libraries(main PRIVATE SDL2::SDL2main)
target_include_directories(main PRIVATE ${SDL2_INCLUDE_DIRS})
