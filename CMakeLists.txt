cmake_minimum_required(VERSION 3.16)
project(arkane C CXX)

file(GLOB IMGUI_SRC
	"imgui.h"
	"imconfig.h"
	"imgui_internal.h"
	"imgui.cpp"
	"imgui_demo.cpp"
	"imgui_draw.cpp"
	"imgui_tables.cpp"
	"imgui_widgets.cpp"
	"imgui_rectpack.cpp"
	"imgui_textedit.cpp"
	"imgui_truetype.cpp"
)

file(GLOB IMGUI_BACKEND_SRC
	"backends/imgui_impl_sdl.h"
	"backends/imgui_impl_sdlrenderer.h"
	"backends/imgui_impl_sdl.cpp"
	"backends/imgui_impl_sdlrenderer.cpp"
)

add_library("imgui" STATIC ${IMGUI_SRC} ${IMGUI_BACKEND_SRC})
target_link_libraries("imgui" PUBLIC SDL2::SDL2-static)

target_include_directories("imgui" PUBLIC "")
target_include_directories("imgui" PUBLIC "backends")