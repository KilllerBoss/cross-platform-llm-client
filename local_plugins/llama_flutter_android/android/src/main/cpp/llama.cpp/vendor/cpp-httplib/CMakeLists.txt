# Header-only stand-in for llama.cpp's vendored cpp-httplib: common/ needs
# just the client API (http.h, download.cpp, hf-cache.cpp). The server-side
# (SSL) build the upstream vendor CMake does is not used here — the server
# is compiled out. Include path is vendor/ so <cpp-httplib/httplib.h> works.
add_library(cpp-httplib INTERFACE)
target_include_directories(cpp-httplib INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}/..")
