# Documentation Makefile
#
# Copyright 2022 Stéphane Caron

# You can also set these variables from the command line.
DOXYGEN      = doxygen
HTMLDIR      = html
REMOTEDIR    = scaron.info:public_html/doc/mpacklog.cpp

.PHONY: clean html open upload

html:
	(cd .. && $(DOXYGEN) $(CURDIR)/Doxyfile)

clean:
	rm -rf $(HTMLDIR)

open:
	firefox $(HTMLDIR)/index.html

upload: clean html
	rsync -auvz --delete-after $(HTMLDIR)/ $(REMOTEDIR)/
