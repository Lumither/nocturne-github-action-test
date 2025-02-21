ARCH := $(shell uname -m)
ifeq ($(ARCH), arm64)
    ARCH := aarch64
endif

GIT_HASH := $(shell git rev-parse --short HEAD)

IMAGE_NAME := ghcr.io/lumither/nocturne-github-action-test-backend

all: release

release:
	docker build -t $(IMAGE_NAME) \
				 -f ./production.containerfile . \
				 --build-arg ARCH=$(ARCH)

tag:
	docker tag $(IMAGE_NAME) $(IMAGE_NAME):$(GIT_HASH)-$(ARCH)

push:
	docker push $(IMAGE_NAME):$(GIT_HASH)-$(ARCH)

.PHONY: all release tag push