CC = /usr/local/cuda/bin/nvcc
LFLAGS += -lopencv_core -lopencv_highgui -lopencv_imgproc -lopencv_imgcodecs -lopencv_videoio -lopencv_video -L/usr/local/lib
CFLAGS += -std=c++11 -g 
INCLUDES += -I/usr/include/opencv4

all-cpu: build-cpu run
all-v1: build-v1 run
all-v2: build-v2 run

build-cpu: 
	$(CC) $(CFLAGS) $(LFLAGS) $(INCLUDES) cpu.cu -o grayscale-average

build-v1: 
	$(CC) $(CFLAGS) $(LFLAGS) $(INCLUDES) $(SRCS) gpu-v1.cu -o grayscale-average

build-v2: 
	$(CC) $(CFLAGS) $(LFLAGS) $(INCLUDES) $(SRCS) gpu-v2.cu -o grayscale-average

run:
	./grayscale-average

prof:
	sudo $(PROFILER) ./grayscale-average