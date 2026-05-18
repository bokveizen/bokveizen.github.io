MAIN = resume
PDF = CV_Fanchen_Bu_latest.pdf
TEX = xelatex
TEXFLAGS = -interaction=nonstopmode -halt-on-error

all: $(PDF)

$(PDF): $(MAIN).tex resume.cls fontawesome.sty linespacing_fix.sty Makefile
	latexmk -xelatex -jobname=$(basename $(PDF)) $(TEXFLAGS) $(MAIN).tex

resume.pdf: resume.tex resume.cls fontawesome.sty linespacing_fix.sty
	$(TEX) $(TEXFLAGS) resume.tex

resume-zh_CN.pdf: resume-zh_CN.tex resume.cls fontawesome.sty linespacing_fix.sty
	$(TEX) $(TEXFLAGS) resume-zh_CN.tex

ifeq ($(OS),Windows_NT)
  # on Windows
  RM = cmd //C del
else
  # on Unix/Linux
  RM = rm -f
endif

clean:
	latexmk -c
	$(RM) *.aux *.bbl *.blg *.log *.out *.synctex.gz *.toc *.lof *.idx *.ilg *.ind *.fls *.fdb_latexmk *.xdv

distclean: clean
	$(RM) *.pdf
