SRC += main.cpp
DEBUG := -g
INC := ./

CC := gcc --std=c99
#CC := clang
CXX := g++ --std=c++14
#CXX := clang++ --std=c++14

WARNS := -pedantic -Wall -Wextra -Wcast-align -Wcast-qual -Wctor-dtor-privacy 
WARNS += -Wdisabled-optimization -Wformat=2 -Winit-self -Wlogical-op -Wmissing-declarations 
WARNS += -Wmissing-include-dirs -Wnoexcept -Wold-style-cast -Woverloaded-virtual -Wredundant-decls 
WARNS += -Wshadow -Wsign-conversion -Wsign-promo -Wstrict-null-sentinel -Wstrict-overflow=5 -Wswitch-default 
WARNS += -Wundef -Wno-unused

CFLAGS := $(DEBUG) -I$(INC) -Wall -O2
CXXFLAGS := $(DEBUG) -I$(INC) $(WARNS) -O2

.PHONY: clean

SRC_OBJ := $(SRC:.cpp=.o)

.c.o:
	$(CC) -c $(CFLAGS) $< -o $@

.cpp.o:
	$(CXX) -c $(CXXFLAGS) $< -o $@

all: $(SRC_OBJ)
	$(CXX) $(SRC_OBJ) -lpthread -o echo-server

clean: 
	rm -f $(SRC_OBJ) echo-server
