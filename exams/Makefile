.PHONY: 2017
2017:			exam-170526.pdf exam-170828.pdf exam-171107.pdf
EXAM_IDS+=		170526 170828 171107

exam-170526.pdf: miunexam
exam-170828.pdf: miunexam
exam-171107.pdf: miunexam


.PHONY: 2016
2016: exam-160601.pdf exam-160816.pdf exam-161027.pdf

exam-160601.pdf: exam-160601.tex miunexam
exam-160816.pdf: exam-160816.tex miunexam
exam-161027.pdf: exam-161027.tex questions-161027.tex miunexam


.PHONY: 2015
2015: infosakb-150601.pdf infosakb-150605.pdf infosakb-150827.pdf

infosakb-150827.pdf: infosakb-150827.tex miunexam
infosakb-150605.pdf: infosakb-150605.tex miunexam
infosakb-150601.pdf: infosakb-150601.tex miunexam


infosak-questions.pdf: infosak-questions.tex



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

#EXAM_DBS+=		$(foreach id,${EXAM_IDS}, questions-${id}.tex)
EXAM_DBS+=		questions-170526.tex
EXAM_DBS+=		questions-161027.tex exam-160816.tex exam-160601.tex
EXAM_DBS+=		infosakb-150827.tex infosakb-150605.tex infosakb-150601.tex
EXAM_DBS+=		./exam-20130603/exam-20130603.tex
EXAM_DBS+=		./exam-20120828/exam-20120828.tex
EXAM_DBS+=		./exam-20120530/exam-20120530.tex



INCLUDE_MIUNTEX=../miuntex
INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/tex.mk
include ${INCLUDE_MAKEFILES}/exam.mk
include ${INCLUDE_MAKEFILES}/miun.depend.mk
