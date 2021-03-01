V = 0-14-0
VER = version/$(V)

.PHONY: help readme ref-man all $(VER)/reference-manual.html

help:
	@echo readme ref-man all

readme: $(VER)/README.html

ref-man: $(VER)/reference-manual.html

all: readme ref-man

$(VER)/README.rst: ${EXACTLY_REPO_DIR}/README.rst
	cp -a ${EXACTLY_REPO_DIR}/README.rst $(VER)

$(VER)/README.html: $(VER)/README.rst exactly.css
	python3 tools/rst2html4.py $(VER)/README.rst > $(VER)/README.html

$(VER)/reference-manual.html:
	python3 ${EXACTLY_REPO_DIR}/src/default-main-program-runner.py help htmldoc > $(VER)/reference-manual.html

