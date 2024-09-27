CXX=g++
CPPFLAGS=-Wall -std=c++14 -fPIC -O2
INCLUDES = -I.

all: build/libHeliosDacAPI.so


build/HeliosDac.o: HeliosDac.cpp
	$(CXX) $(CPPFLAGS) $(INCLUDES) -c -o $@ $^

build/HeliosDacAPI.o: shared_library/HeliosDacAPI.cpp
	$(CXX) $(CPPFLAGS) $(INCLUDES) -c -o $@ $^

build/libHeliosDacAPI.so: build/HeliosDac.o build/HeliosDacAPI.o
	$(CXX) -shared -o $@ $^ -lusb-1.0

.PHONY : clean
clean:
	rm build/*.o build/*.so