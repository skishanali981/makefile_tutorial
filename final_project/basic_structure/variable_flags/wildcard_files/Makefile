DEBUG = 1
EXECUTABLE = main

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -o0
else
CXXFLAGS += -o3
endif

CXX = g++
CXXFLAGS = -Wextra -Wpedantic -Wall -std=c++17


COMPILER_CALL = $(CXX) $(CXXFLAGS)

CXX_SOURCES = $(wildcard *.cc)
CXX_OBJECTS = $(patsubst %.cc, %.o, $(CXX_SOURCES))

build: $(CXX_OBJECTS)
	echo $(CXX_SOURCES)
	$(COMPILER_CALL) $(CXX_OBJECTS) -o $(EXECUTABLE)

my_lib.o:
	$(COMPILER_CALL) -c my_lib.cc

main.o:
	$(COMPILER_CALL) -c main.cc

execute:
	./$(EXECUTABLE)

clean:
	rm -rf *.o
	rm -rf $(EXECUTABLE)


#####################
#	TARGET	    #
#####################

# $@ : Name of the target
# $< : Name of the first Dependency
# $^ : Name of all the prerequisites

%.o : %.cc
	$(COMPILER_CALL) -c $< -o $@
