
TARGET = raspberrypi_capture
LIBS = -lm
CC = gcc
CFLAGS = -g -Wall

.PHONY: default all clean

default: $(TARGET)
all: default

OBJECTS = $(patsubst %.c, %.o, $(wildcard *.c))
HEADERS = $(wildcard *.h)

%.o: %.c $(HEADERS)
	$(CC) -I/usr/local/include/opencv -I/usr/local/include/opencv2 -L/usr/local/lib/ $(CFLAGS) -c $< -o $@ -lopencv_core -lopencv_imgproc -lopencv_highgui -lopencv_ml -lopencv_video -lopencv_features2d -lopencv_calib3d -lopencv_objdetect -lopencv_contrib -lopencv_legacy -lopencv_stitchin

.PRECIOUS: $(TARGET) $(OBJECTS)

$(TARGET): $(OBJECTS)
	$(CC) -I/usr/local/include/opencv -I/usr/local/include/opencv2 -L/usr/local/lib/ $(OBJECTS) -Wall $(LIBS) -o $@ -lopencv_core -lopencv_imgproc -lopencv_highgui -lopencv_ml -lopencv_video -lopencv_features2d -lopencv_calib3d -lopencv_objdetect -lopencv_contrib -lopencv_legacy -lopencv_stitching

clean:
	-rm -f *.o
	-rm -f $(TARGET)

