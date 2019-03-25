PUB_FILES+= index.html

SUBDIR+= 	intro
SUBDIR+= 	conclusion

SUBDIR_GOALS= 	all clean distclean publish

PUB_SERVER?=ver.miun.se
PUB_DIR?= 	/srv/web/svn/courses/security/infosakb
PUB_USER?=
PUB_GROUP?= svn


index.md: $(foreach f,${SUBDIR},$f/$f.md)
	${RM} $@
	for f in $^; do ${CAT} $$f >> $@; echo >> $@; done

$(addsuffix /%,${SUBDIR}):
	${MAKE} -C $(dir $@) $(notdir $@)


.PHONY: clean
clean:
	${RM} index.md index.html


INCLUDE_MAKEFILES=../makefiles
include ${INCLUDE_MAKEFILES}/subdir.mk
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/pub.mk
