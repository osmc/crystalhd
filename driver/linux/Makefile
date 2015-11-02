#
#  Broadcom Crystal HD (BCM970012) controller Makefile.
#
#
KDIR:=$(shell pwd)/../../../


INCLUDES  = -I$(KDIR)/include
INCLUDES += -I$(src)/../../include
INCLUDES += -I$(src)/../../include/link
INCLUDES += -I$(src)/../../include/flea

EXTRA_CFLAGS   = -D__KERNEL__ -DMODULE $(INCLUDES) $(INC)
EXTRA_CFLAGS  += -Wall -Wstrict-prototypes -Wno-trigraphs -Werror -O2

OBJ :=	crystalhd_lnx.o \
	crystalhd_misc.o \
	crystalhd_cmds.o \
	crystalhd_hw.o \
	crystalhd_linkfuncs.o \
	crystalhd_fleafuncs.o \
	crystalhd_flea_ddr.o

PWD = $(shell pwd)

obj-m := crystalhd.o
	crystalhd-objs := $(OBJ)

all:
	$(MAKE) -C $(KDIR) SUBDIRS=$(PWD) modules

clean:
	rm -f *.map *.list *.o *.ko crystalhd.mod.c $(OBJ)

distclean:
	rm -f *.map *.list *.o *.ko crystalhd.mod.c $(OBJ)
	rm -f configure config.status config.log *~*
	rm -rf autom4te.cache
	rm -f Makefile
	rm -f Module.symvers
