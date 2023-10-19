#Variables can only be strings
#single or double quptes for variable names has no meaning for make

DEBUG = 1
EXECUTABLE_NAME = main
# CC: Program for compiling C programs; default cc
# CXX: program for compiling c++ programs; default g++
# CFLAGS: Extra Flags to give to c compiler
# CXXFLAGS: Extra flags to give to the c++ compiler
# CPPFLAGS: extra flags to give to the c preprocessor
# LDFLAGS: Extra flags to give to the Linker

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -o0
else
CXXFLAGS += -o3
endif

CXX = g++
CXXFLAGS = -Wall -Wextra -Wpedantic -std=c++17
LDFLAGS = -lmath 

COMPILER_CALL = $(CXX) $(CXXFLAGS)

build: my_lib.o main.o
	$(COMPILER_CALL) main.o my_lib.o -o $(EXECUTABLE_NAME)

main.o:
	$(COMPILER_CALL) -c main.cc 
my_lib.o:
	$(COMPILER_CALL) -c my_lib.cc 

