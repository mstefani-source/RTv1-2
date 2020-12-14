cmake_minimum_required(VERSION 3.17)
project(RTv1 C)

set(CMAKE_C_STANDARD 99)
set(APP_NAME RTv1)
set(SRC_DIR ${PROJECT_SOURCE_DIR}/sources})

include_directories(includes)
include_directories(libft/includes)
include_directories(/usr/local/include/)

link_directories(libft)
link_directories(SDL2/lib)

file(GLOB CF "libft/*.c"
        "sources/*.c"
        "sources/controllers/*.c"
        "sources/parser/*.c"
        "gnl/*.c"
        "libft/list_funcs/*.c"
        "libft/memory_funcs/*.c"
        "libft/print_funcs/*.c"
        "libft/read_funcs/*.c"
        "libft/string_funcs/*.c"
        "libft/utility_funcs/*.c"
        "libft/print_funcs/printf_src/*.c")


add_executable(RTv1 ${CF})

target_link_libraries(RTv1
        LINK_PUBLIC -lft -lm -lSDL2 -lSDL2_image -lOpenCL)
