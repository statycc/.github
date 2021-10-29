## Put this Makefile in your project directory---i.e., the directory
## containing the paper you are writing. Assuming you are using the
## rest of the toolchain here, you can use it to create .html, .tex,
## and .pdf output files (complete with bibliography, if present) from
## your markdown file. 
## -	Change the paths at the top of the file as needed.
## -	Using `make` without arguments will generate html, tex, and pdf 
## 	output files from all of the files with the designated markdown
##	extension. The default is `.md` but you can change this. 
## -	You can specify an output format with `make tex`, `make pdf` or 
## - 	`make html`. 
## -	Doing `make clean` will remove all the .tex, .html, and .pdf files 
## 	in your working directory. Make sure you do not have files in these
##	formats that you want to keep!

## Markdown extension (e.g. md, markdown, mdown).
MEXT = md

## All markdown files in the working directory
SRC = $(wildcard *.$(MEXT))

PDFS=$(SRC:.md=.pdf)
HTML=$(SRC:.md=.html)

all:	$(HTML) $(PDFS)

pdf:	clean $(PDFS)

html:	clean $(HTML)

%.html:	%.md
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
	 $< | tidy  --doctype html5 --tidy-mark no --wrap 0 --hide-comments yes --output-xhtml no --output-html true --quiet yes --show-warnings no -o $@

# 	--highlight-style=../VisualCs.theme \

# Available styles:
#pygments	
#tango
#haddock
#pygments
#espresso
#zenburn
#kate
#monochrome
#breezedark

	
%.pdf:	%.md
# 	pandoc --pdf-engine=xelatex --citeproc -M date="$$(LANG=en_us_88591 date '+%B  %e, %Y')" -o $@ $<

clean:
	rm -f index.html index.pdf
