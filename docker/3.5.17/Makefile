IMAGE_VERSION := 3.5.17

docker build -f Dockerfile --network=host -t eraft/etcd-stack:$(IMAGE_VERSION) .

default: image

image:
	docker build -f Dockerfile --network=host -t eraft/etcd-stack:3.5.17 .