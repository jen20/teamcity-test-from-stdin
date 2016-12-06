NAME ?= $(shell basename "$(CURDIR)")
SOURCE_FILES = $(shell find $(CURDIR) -type f -name '*.go')

default: help

bin: bin/$(NAME) ## Build application binary

bin/$(NAME): $(SOURCE_FILES)
	go build -o "bin/$(NAME)" .

.PHONY: clean
clean:
	rm -r $(CURDIR)/bin
	rm -r $(CURDIR)/pkg

.PHONY: help
help:
	@echo "Valid targets:"
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-15s\033[0m %s\n", $$1, $$2}'
