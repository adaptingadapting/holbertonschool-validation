lint: ## makes sure the code is clean and nice
	golangci-lint run

build:  lint check ## builds the website with go hugo
	hugo
	go build -o awesome-api

run: ## runs the application in the background
	./awesome-api > ./awesome-api.log 2>&1 &

stop: ## stops the app with the command kill
	pkill awesome-api

clean: ## sopts the app and deletes the awesome api binary and the log file
	rm -rf dist
	rm -f awesome-api awesome-api.log
	rm -f coverage-units.out
	rm -f coverage-integrations.out

test: unit-tests integration-tests ## tests

unit-tests: ## executes the unit tests for the file
	go test -v -short -coverprofile=coverage-units.out

integration-tests: ## integrations tests
	go test -v -coverprofile=coverage-integrations.out

help: ## usage
	@awk -F ': ' '/^[^#].*: /{printf "  %-15s%s\n", $$1, $$2}' $(MAKEFILE_LIST)

check: ## checks for bad markdown or dead links
	markdownlint content/posts/*
	markdown-link-check content/posts/*

validate: ## validates the html with the holberton w3c validator
	./W3C-Validator/w3c_validator.py ./dist/index.html || true
