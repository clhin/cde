MAINTAINERCLEANFILES = Makefile.in

appdefaultsdir = $(CDE_INSTALLATION_TOP)/app-defaults/C

bin_PROGRAMS = dthello

dthello_LDADD = $(DTCLIENTLIBS) $(XTOOLLIB) $(TIRPCLIB)

if SOLARIS
dthello_LDADD += -lgen
endif

dthello_SOURCES = dthello.c

dist_appdefaults_DATA = Dthello

CPP_TARGETS = Dthello
CLEANFILES = $(CPP_TARGETS)
