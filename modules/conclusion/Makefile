PUB_FILES+= 	conclusion.html
PUB_FILES+= 	gapproject.pdf
PUB_FILES+= 	reading.html

PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/infosakb
PUB_USER?=
PUB_GROUP?= 	svn


.PHONY: all
all: ${PUB_FILES}

gapproject.pdf: ism/gapproject/gapproject.pdf
	${LN} $< $@

ism/gapproject/%:
	${MAKE} -C $(dir $@) $(notdir $@)


conclusion.tex:
	${LN} ism/gapproject/abstract.tex $@

conclusion.bib:
	${LN} ism/gapproject/gapproject.bib $@


reading.html: reading.md literature.bib
	pandoc -s --bibliography=literature.bib -o $@ $<

literature.bib: literature.bib($(shell find .. -name \*.bib))


.PHONY: clean
clean:
	${RM} ${PUB_FILES}
	${RM} conclusion.tex conclusion.bib
	${MAKE} -C ism/gapproject clean
	${RM} reading.html
	${RM} literature.bib

.PHONY: distclean
distclean:
	${MAKE} -C ism/gapproject distclean


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk

../%:
	${MAKE} -C $(dir $@) $(notdir $@)
