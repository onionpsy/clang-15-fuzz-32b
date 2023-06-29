cmake_minimum_required(VERSION 3.16)
project(test)

set(global_flags
    -m32
    -g
    -O0
    -fsanitize=fuzzer
)

add_compile_options(${global_flags})
add_link_options(${global_flags} -fuse-ld=lld)

add_executable(fuzz "fuzz.cpp")
