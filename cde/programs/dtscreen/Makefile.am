MAITAINERCLEANFILES = Makefile.in

bin_PROGRAMS = dtscreen

dtscreen_LDADD = $(DTCLIENTLIBS) $(XTOOLLIB)

if SOLARIS
dtscreen_LDADD += -lgen
endif

dtscreen_SOURCES = blank.c dtscreen.c flame.c hopalong.c hsbramp.c	\
		   image.c life.c pyro.c qix.c resource.c rotor.c	\
		   swarm.c usleep.c worm.c dtscreen.h

appdefaultsdir = $(CDE_INSTALLATION_TOP)/app-defaults/C

dist_appdefaults_DATA = Dtscreen

CPP_TARGETS = Dtscreen
CLEANFILES = $(CPP_TARGETS)
