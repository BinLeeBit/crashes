#--------------------------------
# jhead makefile for Unix
#--------------------------------
OBJ=.
SRC=.
CFLAGS:= $(CFLAGS) -O3 -Wall

all: jhead

objs = $(OBJ)/jhead.o $(OBJ)/jpgfile.o $(OBJ)/jpgqguess.o $(OBJ)/paths.o \
	$(OBJ)/exif.o $(OBJ)/iptc.o $(OBJ)/gpsinfo.o $(OBJ)/makernote.o 

$(OBJ)/%.o:$(SRC)/%.c
	${CC} -fsanitize=address -fno-omit-frame-pointer -O1 $(CFLAGS) -c $< -o $@

jhead: $(objs) jhead.h
	${CC} -fsanitize=address -fno-omit-frame-pointer -O1 $(LDFLAGS) -o jhead $(objs) -lm

clean:
	rm -f $(objs) jhead

install:
	cp jhead ${DESTDIR}/usr/local/bin/
