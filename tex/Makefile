all: cv.pdf

%.pdf: %.tex works.bib
	pdflatex $* && bibtex $* && pdflatex $* && pdflatex $*

%.docx: %.tex works.bib ieee.csl
	pandoc -s $< --citeproc --bibliography=references.bib --reference-doc=proposal_template.docx --csl=ieee.csl -o $@

.PHONY: clean
clean:
	rm -f *.aux *.out *.bbl *.log *.blg
