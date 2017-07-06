.PHONY: all
all: .helloworld

REV=b000002

.helloworld: helloworld-linux-amd64 Dockerfile
	docker build -t quay.io/ntfrnzn/helloworld:master-${REV} .
	touch $@

helloworld-linux-amd64: helloworld.go
	env GOOS=linux GOARCH=amd64 go build -ldflags="-X main.rev=${REV}" -o $@ $*

.PHONY: clean
clean:
	rm -f .helloworld helloworld-linux-amd64

