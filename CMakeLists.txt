# Fichier : CMakeLists.txt (à la RACINE)

cmake_minimum_required(VERSION 3.10)
project(calculator_project C)

enable_testing() 

add_subdirectory(include) 
add_subdirectory(src)
