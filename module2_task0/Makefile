build: ## builds the website with go hugo
	hugo
	go build -o awesome-api

run: ## runs the application in the background
	./awesome-api > ./awesome-api.log 2>1& &

stop: ## stops the app with the command kill
	kill "$(pgrep awesome-api)"

clean: ## sopts the app and deletes the awesome api binary and the log file
	kill "$(pgrep awesome-api)"
	rm ./awesome-api ./awesome-api.log

test: ## tests
	curl http://localhost:9999
	curl http://localhost:9999/health

help: ## usage
	@awk -F ': ' '/^[^#].*: /{printf "  %-15s%s\n", $$1, $$2}' $(MAKEFILE_LIST)
