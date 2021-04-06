V = 0-15-0
VER = version/$(V)

.PHONY: help readme ref-man all $(VER)/reference-manual.html

help:
	@echo readme ref-man all

readme: $(VER)/README.html $(VER)/logotype.jpg

ref-man: $(VER)/reference-manual.html

all: readme ref-man

$(VER)/README.rst: ${EXACTLY_REPO_DIR}/README.rst
	cp -a ${EXACTLY_REPO_DIR}/README.rst $(VER)

$(VER)/README.html: $(VER)/README.rst exactly.css
	python3 tools/rst2html4.py $(VER)/README.rst > $(VER)/README.html

$(VER)/logotype.jpg: ${EXACTLY_REPO_DIR}/logotype.jpg
	cp -a ${EXACTLY_REPO_DIR}/logotype.jpg $(VER)

$(VER)/reference-manual.html:
	python3 ${EXACTLY_REPO_DIR}/src/default-main-program-runner.py help htmldoc > $(VER)/reference-manual.html

