# Makefile for compiling with MinGW GCC on Cygwin

CC = i686-w64-mingw32-gcc
CXX = i686-w64-mingw32-g++

all: ray display

ray: CFLAGS = -O3 -w
ray: cal.o ext.o fil.o hit.o int.o mth.o ray.o rnd.o tex.o val.o
	$(CC) -s -o $@ $^

display.o: display.cpp
	$(CXX) $(CFLAGS) $(CXXFLAGS) -c -o $@ $^
displayres.o: display.rc
	windres --target=pe-i386 $^ $@

display: CFLAGS = -O3
display: display.o displayres.o
	$(CXX) -mwindows -s -o $@ $^ -mwindows -llibpng -lz -lcomctl32

clean:
	rm -f *.o

