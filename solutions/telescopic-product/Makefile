CXX ?= g++
CFLAGS ?= -std=c++11 -Wall -O2 -Wno-sign-compare -march=native -g -I../../commonlib/
LDFLAGS ?= 
SRCS := $(shell find . -name '*.cpp')
BINS := decomposition basic

.PHONY: clean all

all: $(BINS)

decomposition: decomposition.o
	$(CXX) $(CFLAGS) $^ -o $@ $(LDFLAGS)

basic: basic.o
	$(CXX) $(CFLAGS) $^ -o $@ $(LDFLAGS)

%.o: %.cpp
	$(CXX) $(CFLAGS) -MMD -c $< -o $@

clean:
	rm -f $(SRCS:%.cpp=%.o) $(SRCS:%.cpp=%.d) $(BINS)

-include $(SRCS:%.cpp=%.d)
