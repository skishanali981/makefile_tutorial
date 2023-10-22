DEBUG = 1
INCLUDE_DIR = include
SOURCE_DIR = src
BUILD_DIR = build


CXX_STANDARD = c++17
CXX_WARNINGS = -Wall -Wextra -Wpedantic
CXX = g++
CXXFLAGS = $(CXX_WARNINGS) -std=$(CXX_STANDARD)
LDFLAGS = 
CPPFLAGS = -I $(INCLUDE_DIR)


ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
EXECUTABLE_NAME = mainDebug
else
CXXFLAGS += -O3
EXECUTABLE_NAME = mainRelease
endif

CXX_COMPILER_CALL = $(CXX) $(CXXFLAGS) $(CPPFLAGS)

CXX_SOURCES = $(wildcard $(SOURCE_DIR)/*.cc)
CXX_OBJECTS = $(patsubst $(SOURCE_DIR)/%.cc, $(BUILD_DIR)/%.o, $(CXX_SOURCES))

#################
##    TARGET   ##
#################
.PHONY: build

build: $(CXX_OBJECTS)
	echo $(CXX_OBJECTS)
	$(CXX_COMPILER_CALL) $(CXX_OBJECTS) -o $(BUILD_DIR)/$(EXECUTABLE_NAME)

$(CXX_OBJECTS):
	echo $(CXX_SOURCES)
	$(CXX_COMPILER_CALL) -c $(CXX_SOURCES)
	mv *.o build/

#my_lib.o:
#	$(CXX_COMPILER_CALL) -c $(SOURCE_DIR)/my_lib.cc -o $(BUILD_DIR)/my_lib.o

#main.o:
#	$(CXX_COMPILER_CALL) -c $(SOURCE_DIR)/main.cc -o $(BUILD_DIR)/main.o

execute:
	./$(BUILD_DIR)/$(EXECUTABLE_NAME)


clean:
	rm -rf $(BUILD_DIR)/*.o
	rm -rf $(BUILD_DIR)/$(EXECUTABLE_NAME)

# PATTERNS

$(BUILD_DIR)/%.o :$(SOURCE_DIR)/%.cc
	$(CXX_COMPILER) -c $< -o $@
