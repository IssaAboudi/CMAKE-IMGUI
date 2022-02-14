cmake_minimum_required(VERSION 3.21)
project(TestImGui)

set(CMAKE_CXX_STANDARD 14)

#fetched these using vcpkg manager
find_package(glfw3 CONFIG REQUIRED) #got by doing 'vcpkg install glfw'
find_package(glad CONFIG REQUIRED) #got by doing 'vcpkg install glad'

#make an imgui folder and put all of these files in the imgui folder
set(IMGUI_SRC
        imgui/main.cpp
        imgui/imgui_impl_opengl3.h
        imgui/imgui_impl_opengl3.cpp
        imgui/imgui_impl_opengl3_loader.h
        imgui/imgui_impl_glfw.h
        imgui/imgui_impl_glfw.cpp
        imgui/imgui.h
        imgui/imgui.cpp
        imgui/imgui_draw.cpp
        imgui/imgui_tables.cpp
        imgui/imgui_widgets.cpp
        imgui/imgui_demo.cpp
        )


#Create the executable and link against all the files provided to us by ImGui
add_executable(TestImGui ${IMGUI_SRC})

target_link_libraries(TestImGui PRIVATE glfw glad::glad) #link the two libraries into the application
