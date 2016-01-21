CC = gcc
CFLAGS = -Wall -g
LIBS = -lusb-1.0 -L../../libusbasp -lusbasp
INCLUDES = -I../../libusbasp/include

SRCS = main.c rfid.c rc522.c config.c
OBJS = $(SRCS:.c=.o)

all: libusbasp.a usbasp_read

usbasp_read: libusbasp.a $(OBJS)
	$(CC) $(LFLAGS) $(OBJS) -o usbasp_read $(LIBS)

libusbasp.a:
	make -C ../../libusbasp

.c.o:
	$(CC) $(CFLAGS) $(INCLUDES) -c $<  -o $@

clean:
	rm -f *.o *.d *_read
	make clean -C ../../libusbasp
