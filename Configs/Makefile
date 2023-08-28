
all: help

help:
	@echo " - outdated           Show outdated Swift packages"
	@echo " - pre-commit:        Place pre-commit hook locally"
	@echo " - tools:             Install developer tools"

outdated:
	mint run swift-outdated

pre-commit:
	mkdir -p .git/hooks/pre-commit
	cp .scripts/pre-commit .git/hooks/pre-commit
	chmod +x .git/hooks/pre-commit
	
tools:
	mint bootstrap
	make pre-commit