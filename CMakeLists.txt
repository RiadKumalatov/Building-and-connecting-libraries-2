cmake_minimum_required(VERSION 3.10)

project(MyDynamicLibraryProject)

# Создание динамической библиотеки
add_library(Leaver SHARED
    Leaver/Leaver.cpp
)

target_include_directories(Leaver PUBLIC
    ${PROJECT_SOURCE_DIR}/Leaver
)

# Создание основного приложения
add_executable(main
    main/main.cpp
)

# Линковка основного приложения с библиотекой
target_link_libraries(main Leaver)
