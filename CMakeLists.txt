cmake_minimum_required(VERSION 3.10)
project(calculator_project C)

# Activer les tests pour CTest
enable_testing()

# Inclure les répertoires du projet
include_directories(include)

# Ajouter les sous-dossiers
add_subdirectory(lib)

# Création de l'exécutable principal
add_executable(calculator main.c)
target_link_libraries(calculator lib)

# -----------------------------
#           TESTS
# -----------------------------

# Addition
add_test(NAME test_add COMMAND calculator add 2 3)
set_tests_properties(test_add PROPERTIES PASS_REGULAR_EXPRESSION "5")

# Soustraction
add_test(NAME test_sub COMMAND calculator sub 3 -2)
set_tests_properties(test_sub PROPERTIES PASS_REGULAR_EXPRESSION "5")

# Multiplication
add_test(NAME test_mul COMMAND calculator mul 5 5)
set_tests_properties(test_mul PROPERTIES PASS_REGULAR_EXPRESSION "25")

# Division
add_test(NAME test_div COMMAND calculator div 1 5)
set_tests_properties(test_div PROPERTIES PASS_REGULAR_EXPRESSION "0.2")

# Carré (nouvelle fonction)
add_test(NAME test_car COMMAND calculator car 5)
set_tests_properties(test_car PROPERTIES PASS_REGULAR_EXPRESSION "25")
