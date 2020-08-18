
CPP=g++

CXX_FLAGS=-Wall -fPIC -std=c++11 

LDFLAGS= -lm -pthread -lstdc++

INCLUDE= -I ./ \
	 -I /opt/intel/openvino_2020.2.120/opencv/include/

LIBS= -Wl,-rpath=/opt/intel/openvino_2020.2.120/opencv/lib -L /opt/intel/openvino_2020.2.120/opencv/lib -lopencv_highgui -lopencv_videoio -lopencv_imgcodecs -lopencv_imgproc -lopencv_core \
      -Wl,-rpath=./ -L./ -ldark


OBJS= demo.o

EXEC= demo

all: $(EXEC)

$(EXEC): demo.o
	$(CPP) $(CXX_FLAGS) -o demo demo.o $(LDFLAGS) $(LIBS)

demo.o : demo.cpp
	$(CPP) $(INCLUDE) $(CXX_FLAGS) -c demo.cpp

.PHONY: clean

clean:
	rm -rf $(OBJS) $(EXEC)
