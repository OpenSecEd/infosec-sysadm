EXAM_NAME= 		DV026G

YEARS+= 		2018
EXAM_IDS-2018= 	180607 180827 190109

EXAM_DATE-180607= 	2018-06-07
EXAM_DATE-180827= 	2018-08-27
EXAM_DATE-190109= 	2019-01-09

define exam_id_template=
.PHONY: $(1)
EXAM_IDS+= 		${EXAM_IDS-$(1)}
$(1): 			$(foreach d,${EXAM_IDS-$(1)}, ${EXAM_NAME}-$d.pdf)
endef

$(foreach y,${YEARS},$(eval $(call exam_id_template,$y)))

.PHONY: 2017
2017:			${EXAM_NAME}-170526.pdf
2017: 			${EXAM_NAME}-170828.pdf
2017: 			${EXAM_NAME}-171107.pdf
EXAM_IDS+=		170526 170828 171107

${EXAM_NAME}-170526.pdf: miunexam
${EXAM_NAME}-170828.pdf: miunexam
${EXAM_NAME}-171107.pdf: miunexam


.PHONY: 2016
2016: 			${EXAM_NAME}-160601.pdf
2016: 			${EXAM_NAME}-160816.pdf
2016: 			${EXAM_NAME}-161027.pdf

${EXAM_NAME}-160601.pdf: ${EXAM_NAME}-160601.tex miunexam
${EXAM_NAME}-160816.pdf: ${EXAM_NAME}-160816.tex miunexam
${EXAM_NAME}-161027.pdf: ${EXAM_NAME}-161027.tex ${EXAM_QNAME}-161027.tex miunexam


.PHONY: 2015
2015: infosakb-150601.pdf infosakb-150605.pdf infosakb-150827.pdf

infosakb-150827.pdf: infosakb-150827.tex miunexam miunmisc
infosakb-150605.pdf: infosakb-150605.tex miunexam miunmisc
infosakb-150601.pdf: infosakb-150601.tex miunexam miunmisc


.PHONY: all
all: 2015 2016 2017 2018

-include individuals.mk


infosak-questions.pdf: infosak-questions.tex
infosak-questions.pdf: miunmisc

EXAM_FLAGS?=	-NCEi

EXAM_TAGS+=		A C E

EXAM_DBS+=		infosak-questions.tex
EXAM_TAGS+=		passwd

# Questions databases from learning modules

#EXAM_DBS+=		../modules/foundations/overview/questions.tex
EXAM_TAGS+=		foundations

#EXAM_DBS+=		../modules/infotheory/basics/questions.tex
EXAM_TAGS+=		infotheory

#EXAM_DBS+=		../modules/appliedcrypto/overview/questions.tex
EXAM_TAGS+=		crypto

#EXAM_DBS+=		../modules/auth/overview/questions.tex
EXAM_TAGS+=		auth

EXAM_DBS+=		../modules/ac/overview/questions.tex
EXAM_TAGS+=		ac

#EXAM_DBS+=		../modules/ac/refmon/questions.tex
#EXAM_TAGS+=		refmon

#EXAM_DBS+=		../modules/usability/overview/questions.tex
EXAM_TAGS+=		usability

#EXAM_DBS+=		../modules/fverif/intro/questions.tex
#EXAM_TAGS+=		fverif

EXAM_DBS+= 		../modules/accountability/overview/questions.tex
EXAM_TAGS+= 	accountability

EXAM_DBS+= 		../modules/software/overview/questions.tex
EXAM_TAGS+= 	software

EXAM_DBS+= 		../modules/trustcomp/overview/questions.tex
EXAM_TAGS+= 	trustcomp

EXAM_DBS+=		../modules/sidechannels/overview/questions.tex
EXAM_TAGS+=		sidechannels

# Questions databases from previously generated exams

EXAM_DBS+=		$(foreach id,${EXAM_IDS}, ${EXAM_QNAME}-${id}.tex)
EXAM_DBS+=		${EXAM_QNAME}-161027.tex
EXAM_DBS+= 		${EXAM_NAME}-160816.tex
EXAM_DBS+= 		${EXAM_NAME}-160601.tex
EXAM_DBS+=		infosakb-150827.tex infosakb-150605.tex infosakb-150601.tex



INCLUDE_MIUNTEX=../miuntex
INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/exam.mk
include ${INCLUDE_MAKEFILES}/miun.depend.mk
