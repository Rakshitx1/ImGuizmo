# Define minimum CMake version
cmake_minimum_required(VERSION 3.20)

# Define project and languages
project(ImGuizmo CXX)

# List of ImGuizmo source files
set(IMGUIZMO_SOURCES
    ImGuizmo.cpp
    GraphEditor.cpp
    ImCurveEdit.cpp
    ImGradient.cpp
    ImSequencer.cpp
)

# List of ImGuizmo header files
set(IMGUIZMO_HEADERS
    ImGuizmo.h
    GraphEditor.h
    ImCurveEdit.h
    ImGradient.h
    ImSequencer.h
    ImZoomSlider.h
)

# Add ImGuizmo library target
add_library(ImGuizmo ${IMGUIZMO_SOURCES} ${IMGUIZMO_HEADERS})

# Include directories for ImGuizmo
target_include_directories(ImGuizmo 
    PUBLIC 
        ${CMAKE_CURRENT_SOURCE_DIR}
)

# Link against ImGui
target_link_libraries(ImGuizmo PUBLIC ImGui)

# Set compiler options
target_compile_features(ImGuizmo PUBLIC cxx_std_17)
