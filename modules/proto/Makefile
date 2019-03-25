PUB_FILES+= 	proto.html

PUB_SERVER?= 	ver.miun.se
PUB_DIR?= 		/srv/web/svn/courses/security/infosakb
PUB_USER?=
PUB_GROUP?= 	svn


.PHONY: all
all: ${PUB_FILES}


proto.md: fverif/intro/README.md

proto.md:
	${RM} $@
	for f in $^; do ${CAT} $$f >> $@; echo >> $@; done

proto.tex: fverif/intro/abstract.tex

proto.tex:
	${RM} proto.tex
	for f in $^; do ${CAT} $$f >> $@; echo >> $@; done

proto.bib: fverif/intro/intro.bib

proto.bib:
	bibtool --preserve.key.case=on --print.deleted.entries=off -s -d -o $@ $^


.PHONY: clean
clean:
	${RM} proto.md proto.html proto.tex proto.bib
	${MAKE} -C proto $@

.PHONY: distclean
distclean:
	${MAKE} -C proto $@


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk
