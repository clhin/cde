MAINTAINERCLEANFILES = Makefile.in

bin_PROGRAMS = dthello

dthello_LDADD = $(DTCLIENTLIBS) $(XTOOLLIB) $(TIRPCLIB)

if SOLARIS
dthello_LDADD += -lgen
endif

dthello_SOURCES = dthello.c

CPP_TARGETS = Dthello
CLEANFILES = $(CPP_TARGETS)
