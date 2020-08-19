.PHONY: help README

help:
	@echo README

README: version/latest/README.html

V = latest

version/$(V)/README.rst: ${EXACTLY_REPO_DIR}/README.rst
	cp -a ${EXACTLY_REPO_DIR}/README.rst version/$(V)

version/$(V)/README.html: version/$(V)/README.rst exactly.css
	python3 tools/rst2html4.py version/$(V)/README.rst > version/$(V)/README.html

$(V)/reference-manual.html:
	python3 ${EXACTLY_REPO_DIR}/src/default-main-program-runner.py help htmldoc > $(V)/reference-manual.html

