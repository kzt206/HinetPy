# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line.
SPHINXOPTS    =
SPHINXBUILD   = sphinx-build
SPHINXPROJ    = HinetPy
SOURCEDIR     = .
BUILDDIR      = _build

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

.PHONY: help Makefile

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

translation: gettext
	sphinx-intl update -p _build/gettext -l zh_CN

html-zh_CN:
	@echo "Building Chinese version HTML files."
	sphinx-intl build
	$(SPHINXBUILD) -b html -d $(BUILDDIR)/doctrees \
		$(SPHINXOPTS) -D language='zh_CN' \
		$(SOURCEDIR) $(BUILDDIR)/html/zh_CN

docs: html html-zh_CN
	@echo
