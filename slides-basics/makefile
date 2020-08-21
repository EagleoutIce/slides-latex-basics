# list all papers
SLIDESTEX := $(shell ls *folien*.tex)
SLIDESPDF := $(addsuffix .pdf,$(basename $(SLIDESTEX)))
CLEANTARGETS := log aux out ind bbl blg lof lot toc idx acn acr alg glg glo gls fls fdb_latexmk auxlock md5 SATZE ZSM UB TOP listing upa ilg TOPIC DEFS vrb snm nav md5
SLIDTAR := pdf tex log mdf aux md5

#create all papers
all:	$(SLIDESPDF)
	for fd in $(CLEANTARGETS); do rm -f ./*.$$fd; done
	for fd in $(SLIDTAR); do rm -f ./*-slidelst.$$fd; done

%.pdf: %.tex
	pdflatex -shell-escape -draftmode -jobname $(basename $@) $<
	pdflatex -shell-escape -jobname $(basename $@) $<


cleantemp:
	for fd in $(CLEANTARGETS); do rm -f ./*.$$fd; done
	for fd in $(SLIDTAR); do rm -f ./*-slidelst.$$fd; done

clean: cleantemp
	rm -f *.pdf
