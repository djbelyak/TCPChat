cmake_minimum_required(VERSION 2.8)          # Проверка версии CMake.
											 # Если версия установленой программы
											 # старее указаной, произайдёт аварийный выход.

project(TCPChat)                      		 # Название проекта

set(SOURCE_SERVER server.cpp)                # Установка переменной со списком исходников для исполняемого файла

set(SOURCE_CLIENT client.cpp)                # Установка переменной со списком исходников для исполняемого файла

set(SOURCE_LIB network.cpp)                  # Тоже самое, но для библиотеки

add_library(network STATIC ${SOURCE_LIB})    # Создание статической библиотеки с именем scaner

add_executable(server ${SOURCE_SERVER})      # Создает исполняемый файл с именем server

add_executable(client ${SOURCE_CLIENT})      # Создает исполняемый файл с именем server

target_link_libraries(server scaner)         # Линковка программы с библиотекой

target_link_libraries(client scaner)         # Линковка программы с библиотекой