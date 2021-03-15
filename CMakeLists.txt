cmake_minimum_required(VERSION 3.0)
project(imgui)

add_library(imgui SHARED
    imconfig.h
    imgui.h
    imgui.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    imgui_internal.h
    imstb_rectpack.h
    imstb_textedit.h
    imstb_truetype.h
    backends/imgui_impl_glfw.cpp backends/imgui_impl_glfw.h
    backends/imgui_impl_opengl3.cpp backends/imgui_impl_opengl3.h
)

add_definitions(-DIMGUI_IMPL_OPENGL_LOADER_GLAD)

target_link_libraries(imgui PRIVATE glad glfw)
target_include_directories(imgui PUBLIC . /backends)