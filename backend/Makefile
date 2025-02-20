ARCH := $(shell uname -m)
ifeq ($(ARCH), arm64)
    ARCH := aarch64
endif

all: release

release:
	docker build -t nocturne-backend \
				 -f ./production.containerfile . \
				 --build-arg ARCH=$(ARCH)
