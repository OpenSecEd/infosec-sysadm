EXAM_NAME= 		DV026G


YEARS+= 		2019

EXAM_IDS-2019+= 190605
EXAM_IDS-2019+= 190829
EXAM_IDS-2019+= 200108

EXAM_DATE-190605= 	2019-06-05
EXAM_DATE-190829= 	2019-08-29
EXAM_DATE-200108= 	2020-01-08


YEARS+= 		2018
EXAM_IDS-2018= 	180607 180827 190109

EXAM_DATE-180607= 	2018-06-07
EXAM_DATE-180827= 	2018-08-27
EXAM_DATE-190109= 	2019-01-09


YEARS+= 		2017
EXAM_IDS-2017=	170526 170828 171107

${EXAM_NAME}-170526.pdf: miunexam
${EXAM_NAME}-170828.pdf: miunexam
${EXAM_NAME}-171107.pdf: miunexam


YEARS+= 		2016
EXAM_IDS-2016= 	160601 160816 161027

${EXAM_NAME}-160601.pdf: ${EXAM_NAME}-160601.tex miunexam
${EXAM_NAME}-160816.pdf: ${EXAM_NAME}-160816.tex miunexam
${EXAM_NAME}-161027.pdf: ${EXAM_NAME}-161027.tex questions-161027.tex miunexam


.PHONY: 2015
2015: infosakb-150601.pdf infosakb-150605.pdf infosakb-150827.pdf

infosakb-150827.pdf: infosakb-150827.tex miunexam miunmisc
infosakb-150605.pdf: infosakb-150605.tex miunexam miunmisc
infosakb-150601.pdf: infosakb-150601.tex miunexam miunmisc


.PHONY: all
all: 2015 ${YEARS}

-include individuals.mk


infosak-questions.pdf: infosak-questions.tex
infosak-questions.pdf: miunmisc


#EXAM_FLAGS?=	-NCEi
EXAM_FLAGS?=	-NCi

EXAM_DBS+= 		$(shell find ../modules -name \*.tex)

EXAM_TAGS+=		A C E
EXAM_TAGS+=		foundations
EXAM_TAGS+=		infotheory
EXAM_TAGS+=		crypto
EXAM_TAGS+=		auth
EXAM_TAGS+=		passwd
EXAM_TAGS+=		ac
EXAM_TAGS+=		usability
EXAM_TAGS+=		proto
EXAM_TAGS+= 	accountability
EXAM_TAGS+= 	software
EXAM_TAGS+= 	trustcomp
EXAM_TAGS+=		sidechannels


# Questions databases from previously generated exams

EXAM_DBS+=		$(foreach id,${EXAM_IDS}, ${EXAM_QNAME}-${id}.tex)


PUB_SERVER?=    ver.miun.se
PUB_DIR?=       /srv/web/svn/courses/security/infosakb/exams
PUB_FILES?=     $(foreach id,$(foreach y,${YEARS}, ${EXAM_IDS-$y}), ${EXAM_NAME}-${id}.pdf)


### Generate targets for all years ###

define exam_id_template=
.PHONY: $(1)
EXAM_IDS+=      ${EXAM_IDS-$(1)}
$(1):           $(foreach d,${EXAM_IDS-$(1)}, ${EXAM_NAME}-$d.pdf)

.PHONY: clean clean-$(1)
clean: clean-$(1)
clean-$(1):
	${RM} $(foreach d,${EXAM_IDS-$(1)}, ${EXAM_NAME}-$d.pdf)
endef

$(foreach y,${YEARS},$(eval $(call exam_id_template,$y)))


### Don't expect questions-%.tex for exams from before 2017 ###

$(foreach exam_id,$(foreach y,2014 2015 2016, ${EXAM_IDS-$y}),\
    $(eval EXAM_QNAME-${exam_id}=${EXAM_NAME}))


### All exams depends on literature.bib ###

${EXAM_NAME}-%.pdf: literature.bib

literature.bib: literature.bib($(shell find ../ -name \*.bib))


.PHONY: clean
clean:
	${RM} literature.bib


INCLUDE_MIUNTEX=../miuntex
INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/pub.mk
include ${INCLUDE_MAKEFILES}/exam.mk
include ${INCLUDE_MAKEFILES}/miun.depend.mk
