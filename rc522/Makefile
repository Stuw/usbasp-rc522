CC = gcc
CFLAGS = -Wall -g
LIBS = -L../../libusbasp -lusbasp -lusb-1.0
INCLUDES = -I../../libusbasp/include

SRCS = main.c rfid.c rc522.c config.c
OBJS = $(SRCS:.c=.o)

all: libusbasp.a usbasp_read

usbasp_read: libusbasp.a $(OBJS)
	$(CC) $(OBJS) -o usbasp_read $(LFLAGS) $(LIBS)

libusbasp.a:
	make -C ../../libusbasp

.c.o:
	$(CC) $(CFLAGS) $(INCLUDES) -c $<  -o $@

clean:
	rm -f *.o *.d *_read
	make clean -C ../../libusbasp
