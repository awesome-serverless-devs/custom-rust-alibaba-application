build-img:
	docker build -t fc-rust-env -f Dockerfile.build .

build: build-img
	docker run --rm -i -v $$(pwd):/opt/rust-demo fc-rust-env bash -c "cd /opt/rust-demo/bootstrap && cargo build"
	mkdir -p pkg
	cp bootstrap/target/debug/bootstrap pkg/
	chmod 755 pkg/bootstrap

.PHONY: build