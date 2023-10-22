DEBUG = 1
INCLUDE_DIR = include
SOURCE_DIR = src
BUILD_DIR = build
ENABLE_WARNING = 1
WARNING_AS_ERROR =1

CXX_STANDARD = c++17
ifeq ($(ENABLE_WARNING), 1)
CXX_WARNINGS = -Wall -Wpedantic -Wextra
else
CXX_WARNINGS =
endif

ifeq ($(WARNING_AS_ERROR), 1)
CXX_WARNINGS += -Werror
endif

CXX = g++
CXXFLAGS = $(CXX_WARNINGS) -std=$(CXX_STANDARD)
CPPFLAGS = -I $(INCLUDE_DIR)
LDFLAGS =

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
EXECUTABLE_NAME = mainDebug
else
CXXFLAGS += -O3
EXECUTABLE_NAME = mainRelease
endif

CXX_COMPILER_CALL = $(CXX) $(CXXFLAGS) $(CPPFLAGS)

CXX_SOURCE = $(wildcard $(SOURCE_DIR)/*.cc)
CXX_OBJECT = $(patsubst $(SOURCE_DIR)/%.cc, $(BUILD_DIR)/%.o, $(CXX_SOURCE))

.PHONY: build clean execute

build: $(CXX_OBJECT)
	$(CXX_COMPILER_CALL) $(CXX_OBJECT) -o $(BUILD_DIR)/$(EXECUTABLE_NAME)

$(CXX_OBJECT): $(CXX_SOURCE)
	$(CXX_COMPILER_CALL) -c $(CXX_SOURCE) 
	mv *.o $(BUILD_DIR)/

clean:
	rm -rf $(BUILD_DIR)/*


execute:
	./$(BUILD_DIR)/$(EXECUTABLE_NAME)

