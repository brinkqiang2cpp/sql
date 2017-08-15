cmake_minimum_required(VERSION 3.1)
project(proj-sql)

# Build directories
SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/bin)
SET(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/lib)
SET(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/lib)

# Testing
enable_testing(true)

# Front end executables
add_subdirectory(bin-dump-sql-text)

# Core libraries
add_subdirectory(lib-dump)
add_subdirectory(lib-sql)

# Transformator libraries
add_subdirectory(lib-dump-sql)
add_subdirectory(lib-sql-text)
