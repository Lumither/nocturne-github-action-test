ARCH := $(shell uname -m)
ifeq ($(ARCH), arm64)
    ARCH := aarch64
endif

all: release

release:
	# docker compose -f prod.compose.yaml build --build-arg ARCH=$(ARCH)
	docker build -t nocturne-backend \
				 -f ./production.containerfile . \
				 --build-arg ARCH=$(ARCH)
