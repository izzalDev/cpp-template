CXX := g++
CXXFLAGS := -Wall -std=c++17

SRC_DIR := src
BUILD_DIR := build

SRCS := $(wildcard $(SRC_DIR)/*.cpp)
OBJS := $(patsubst $(SRC_DIR)/%.cpp, $(BUILD_DIR)/%.o, $(SRCS))
TARGET := $(BUILD_DIR)/{{cookiecutter.project_title}}

all: $(TARGET)

$(TARGET): $(OBJS)
	@$(CXX) -o $@ $^

$(OBJS): $(SRCS) | $(BUILD_DIR)
	@$(CXX) $(CXXFLAGS) -c $< -o $@

$(BUILD_DIR):
	@mkdir -p $(BUILD_DIR)

clean:
	@rm -rf $(BUILD_DIR)

run: all
	@./$(TARGET)

.PHONY: all clean run





