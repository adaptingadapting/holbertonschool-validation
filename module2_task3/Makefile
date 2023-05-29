lint: ## makes sure the code is clean and nice
	golangci-lint run

build:  lint ## builds the website with go hugo
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

unit-tests: ## executes the unit tests for the fil
