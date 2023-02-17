## Markdown extension (e.g. md, markdown, mdown).
MEXT = md
## All markdown files in the working directory
SRC = $(wildcard *.$(MEXT))
HTML=$(SRC:.md=.html)

all: $(HTML)

%.html:	%.$(MEXT)
	pandoc \
	--standalone \
	--email-obfuscation=references \
	-c ../../web/style/style.css \
	--columns=10000 \
	--section-divs \
	--toc \
	--toc-depth=1 \
	-t html5 \
	--citeproc \
	-M date="$$(LANG=en_us_88591 date '+%B  %e, %Y')" \
	-H head.html \
	 $< | tidy  --doctype html5 --tidy-mark no --wrap 0 --hide-comments yes --output-xhtml no --output-html true --quiet yes --show-warnings no -o $@ || [ $$? -eq 1 ] && true

clean:
	rm -f index.html
