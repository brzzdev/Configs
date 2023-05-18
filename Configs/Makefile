
all: help

help:
	@echo " - pre-commit:        Place pre-commit hook locally"
	@echo " - tools:             Install developer tools"

SWIFTFORMAT_PATH=$(shell which swiftformat)

pre-commit:
	echo "#!/bin/bash" > .git/hooks/pre-commit
	echo "./.git-format-staged --formatter \"$(SWIFTFORMAT_PATH) stdin --stdinpath '{}'\" \"*.swift\"" > .git/hooks/pre-commit
	chmod +x .git/hooks/pre-commit
	
tools:
	mint bootstrap
	make pre-commit