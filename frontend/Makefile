GIT_HASH := $(shell git rev-parse --short HEAD)

IMAGE_NAME := ghcr.io/lumither/nocturne-github-action-test-frontend

all: release

release:
	docker build -t $(IMAGE_NAME) \
				 -f ./production.containerfile . \

tag:
	docker tag $(IMAGE_NAME) $(IMAGE_NAME):$(GIT_HASH)-$(ARCH)

push:
	docker push $(IMAGE_NAME):$(GIT_HASH)-$(ARCH)

.PHONY: all release tag push