# Fichier : CMakeLists.txt (à la RACINE)

cmake_minimum_required(VERSION 3.10)
project(calculator_project C)

# Active CTest pour les tests unitaires
enable_testing() 

# -----------------------------
#   Inclure les sous-dossiers
# -----------------------------
# 1. Inclut le dossier des headers
add_subdirectory(include) 
# 2. Inclut le dossier des sources, ce qui lancera src/CMakeLists.txt
add_subdirectory(src)
