project(ImGuiApp)

add_executable(
  ${PROJECT_NAME}

  main.cpp

  imgui/imgui.cpp imgui/imgui_demo.cpp imgui/imgui_tables.cpp imgui/imgui_widgets.cpp imgui/imgui_draw.cpp
  imgui/backends/imgui_impl_opengl3.cpp imgui/backends/imgui_impl_sdl.cpp

)

target_include_directories(
  ${PROJECT_NAME}
  PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui/backends/
)

find_package(SDL2 REQUIRED)
find_package(GLEW REQUIRED)
target_link_libraries(
  ${PROJECT_NAME}
  PRIVATE
    SDL2::SDL2-static SDL2::SDL2main GLEW::GLEW
)