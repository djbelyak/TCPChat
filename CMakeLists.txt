cmake_minimum_required(VERSION 2.8)          # Ïðîâåðêà âåðñèè CMake.
                                                                                         # Åñëè âåðñèÿ óñòàíîâëåíîé ïðîãðàììû
                                                                                         # ñòàðåå óêàçàíîé, ïðîèçàéä¸ò àâàðèéíûé âûõîä.

project(TCPChat)                                       # Íàçâàíèå ïðîåêòà

set(SOURCE_SERVER server.cpp)                # Óñòàíîâêà ïåðåìåííîé ñî ñïèñêîì èñõîäíèêîâ äëÿ èñïîëíÿåìîãî ôàéëà

set(SOURCE_CLIENT client.cpp)                # Óñòàíîâêà ïåðåìåííîé ñî ñïèñêîì èñõîäíèêîâ äëÿ èñïîëíÿåìîãî ôàéëà

set(SOURCE_LIB network.cpp)                  # Òîæå ñàìîå, íî äëÿ áèáëèîòåêè

add_library(network STATIC ${SOURCE_LIB})    # Ñîçäàíèå ñòàòè÷åñêîé áèáëèîòåêè ñ èìåíåì scaner

add_executable(server ${SOURCE_SERVER})      # Ñîçäàåò èñïîëíÿåìûé ôàéë ñ èìåíåì server

add_executable(client ${SOURCE_CLIENT})      # Ñîçäàåò èñïîëíÿåìûé ôàéë ñ èìåíåì server

target_link_libraries(server network pthread)         # Ëèíêîâêà ïðîãðàììû ñ áèáëèîòåêîé

target_link_libraries(client network pthread)         # Ëèíêîâêà ïðîãðàììû ñ áèáëèîòåêîé
