##########################################################################
# User configuration and firmware specific object files	
##########################################################################

OBJS =

OBJS += ff.o
OBJS += diskio.o
OBJS += iobase.o
OBJS += mmc.o
OBJS += at45db041d.o

LIBNAME=fat

##########################################################################
# GNU GCC compiler flags
##########################################################################
ROOT_PATH?= ..
INCLUDE_PATHS = -I$(ROOT_PATH) -I../core -I.

include $(ROOT_PATH)/Makefile.inc

LIBFILE=lib$(LIBNAME).a
##########################################################################
# Compiler settings, parameters and flags
##########################################################################

all: $(LIBFILE)

$(LIBFILE): $(OBJS)
	$(AR) rcs $@ $(OBJS)
	
%.o : %.c
	$(CC) $(CFLAGS) -o $@ $<

clean:
	rm -f $(OBJS) $(LIBFILE)

ff.o: ff.c ffconf.h diskio.h ff.h integer.h

