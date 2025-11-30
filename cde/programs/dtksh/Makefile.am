MAINTAINERCLEANFILES = Makefile.in

CLEANFILES = init.c DtFuncs.dtsh

SUBDIRS = examples

kshdir = ${libdir}/dtksh

dist_ksh_SCRIPTS = DtFuncs.dtsh

KSH93SRC = ./ksh93

KSH93LIBSHELL = $(KSH93SRC)/lib/libshell.a

bin_PROGRAMS = dtksh

BUILT_SOURCES = init.c

dtksh_CPPFLAGS = -I$(KSH93SRC)/include/ast -I$(KSH93SRC)/src/cmd/ksh93/include \
		 -I$(KSH93SRC)/src/cmd/ksh93 -I${srcdir}/lib/DtPrint \
		 -I${srcdir}/lib/DtHelp \
		 -D_PACKAGE_ast -DKSHELL \
		 '-DERROR_CONTEXT_T=Error_context_t' \
		 -D_API_ast=20100309 -DBUILD_DTKSH

dtksh_LDADD = $(DTCLIENTLIBS) ksh93/src/cmd/ksh93/pmain.o $(XTOOLLIB) \
	      libshell.a $(KSH93SRC)/lib/libcmd.a $(KSH93SRC)/lib/libast.a \
	      $(KSH93SRC)/lib/libdll.a

if SOLARIS
dtksh_LDADD += -lsecdb -lsocket -lnsl
endif

dtksh_SOURCES = init.c \
                widget.c \
                dtkcvt.c \
                dtkcmds.c \
                XtCvtrs.c \
                xmcvt.c \
                xmcmds.c \
                xmwidgets.c \
                extra.c \
                msgs.c

ksh93/bin/ksh:
	ksh93/bin/package flat make

init.c: ksh93/bin/ksh
	$(CP) ksh93/src/cmd/ksh93/sh/init.c ./

libshell.a: $(KSH93SLIBSHELL) dtksh-init.o
	$(CP) $(KSH93LIBSHELL) libshell.a; \
	$(AR) d libshell.a init.o; \
	$(AR) cq libshell.a dtksh-init.o

#Don't run this if you don't have CDE installed, 
#it doesn't know where to find our shared libs otherwise
check-local:
	./dtksh -c true && ksh93/bin/shtests --posix --utf8 SHELL=.libs/dtksh

clean-local:
	ksh93/bin/package clean

DtFuncs.dtsh:
	$(CP) DtFuncs.sh DtFuncs.dtsh
