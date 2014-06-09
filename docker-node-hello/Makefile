install:
	npm install

build:
	docker build -t nodetest .

run:
	node index.js

run-container:
	docker run -p 49000:8080 -d nodetest 

test:
	curl localhost

clean:
	rm -rf node_modules


.PHONY: install build run test clean
