KVERS?=$(shell uname -r)
obj-m := awusb.o
KDIR := /lib/modules/${KVERS}/build
PWD := $(shell pwd)

all:
	cd $(KDIR) && $(MAKE) -C $(KDIR) M=$(PWD) modules
clean:
	cd $(KDIR) && $(MAKE) -C $(KDIR) M=$(PWD) clean
	rm -rf Module.markers module.order module.sysvers

install: awusb.ko
	install -d /lib/modules/${KVERS}/
	install $< /lib/modules/${KVERS}/
