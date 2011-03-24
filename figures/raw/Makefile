# Makefile to produce the article.
LATEX  =  TEXINPUTS=.//: BSTINPUTS=.//: latex
DVIPS  =  dvips
FIGURES = Flux.comp.CR.eps \
	Fermi.comp.DM.eps \
	flux.IRcomp.v8.0.1deg.1.6T.SubMass.elmu.SF300.noMW.woGal.eps \
	flux.BMcomp.v8.0.1deg.1.6T.SubMass.IR2.noMW.woGal_raw.eps \
	flux.IRcomp.v8.0.1deg.1.6T.SubMass.elmu.SF300.noMW.woGal_raw.eps \
	dens.prof_raw.eps \
	Fermi.comp.CR.diff.eps

.PRECIOUS: $(FIGURES)

default:  Flux.comp.CR.eps

#	perl -ane '{ s/%%BoundingBox: [-0-9]+/%%BoundingBox: 135/g; print}' $*.eps > tmp.eps; \

%.eps: %_raw.eps %.tex
	(latex $*.tex; \
	dvips -E -o $*.eps $*.dvi; \
	perl -ane '{ s/%%BoundingBox: [-0-9]+/%%BoundingBox: 132/g; print}' $*.eps > tmp.eps; \
	mv tmp.eps $*.eps; \
	rm -f *.dvi *.log *.aux)

clean:
	rm -f *.log *.toc *.aux *.dvi *.bak *.blg *.obj *.out

realclean:
	rm -f *.log *.toc *.aux *.dvi *.obj *.bak *.bbl *.blg *.brf \
              *.ps */*.ps *~ */*~ *.bak */*.bak 








