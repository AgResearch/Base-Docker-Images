VERSION=1.1.4
BUILD_DATE=`date -u +"%Y-%m-%dT%H:%M:%SZ"`

default: build

build:
	docker build \
	--tag agresearch\/thesnppit\:$(VERSION) --build-arg VERSION=$(VERSION) --build-arg BUILD_DATE=$(BUILD_DATE) .