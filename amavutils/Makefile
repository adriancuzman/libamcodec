M_PREFIX=$(PREFIX)

TARGET = libamavutils.so

TARGET_OBJS=amaudioutils.o amconfigutils.o amdisplayutils.o ammodule.o amsysfsutils.o Amvideoutils.o itemlist.o\

INSTALL_DIR=${M_PREFIX}/lib

LDFLAGS += -shared -lm -lrt

CFLAGS+=-O2 -fPIC
CFLAGS+=-I$(shell pwd) -I$(shell pwd)/include -I$(shell pwd)/../amcodec/include -I${PREFIX}/include -I${PREFIX}/usr/include -L${PREFIX}/lib -L${PREFIX}/usr/lib

export CC CFLAGS

all: $(TARGET) 

$(TARGET): $(TARGET_OBJS)
	echo "CC=$(CC)"
	echo "LD=$(LD)"
	echo "CFLAGS=$(CFLAGS)"
	echo "LDFLAGS=$(LDFLAGS)"
	$(CC) $(CFLAGS) $(LDFLAGS) $(TARGET_OBJS:%.o=%.c) -o $@  


install:$(TARGET)
	-install -m 555 ${TARGET} $(INSTALL_DIR)

clean:
	-rm -rf *.o $(TARGET)