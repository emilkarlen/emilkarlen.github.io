V = dev
# V=X-Y-Z | dev
VD = version/$(V)

.PHONY: help readme ref-man all clean $(VD)/reference-manual.html venv-clean

help:
	@echo Targets: readme ref-man all clean venv venv-clean
	@echo
	@echo Current version: $(V)
	@echo
	@echo 'SETUP'
	@echo '  * Set version (in this Makefile). Format: X-Y-Z'
	@echo '  * Env var EXACTLY_REPO_DIR must be set (with obvious contents)'
	@echo
	@echo 'NOTE Build should be done in a PYTHON VIRTUAL ENVIRONEMNT'
	@echo 'First, create it with with: make venv'
	@echo 'The activate before making, e.g.: . venv/bin/activate'

readme: $(VD) $(VD)/README.html $(VD)/logotype.jpg

ref-man: $(VD) $(VD)/reference-manual.html

$(VD):
	mkdir $(VD)

all: readme ref-man

clean:
	rm -rf $(VD)

venv:
	python3 -m venv venv
	. venv/bin/activate; pip install docutils

venv-clean:
	rm -rf venv

$(VD)/README.rst: ${EXACTLY_REPO_DIR}/README.rst
	cp -a ${EXACTLY_REPO_DIR}/README.rst $(VD)

$(VD)/README.html: $(VD)/README.rst exactly.css
	rst2html4.py $(VD)/README.rst > $(VD)/README.html

$(VD)/logotype.jpg: ${EXACTLY_REPO_DIR}/logotype.jpg
	cp -a ${EXACTLY_REPO_DIR}/logotype.jpg $(VD)

$(VD)/reference-manual.html:
	python3 ${EXACTLY_REPO_DIR}/src/default-main-program-runner.py help htmldoc > $(VD)/reference-manual.html

