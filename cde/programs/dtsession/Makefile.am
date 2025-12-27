MAINTAINERCLEANFILES = Makefile.in

bin_PROGRAMS = dtsession

bin_SCRIPTS = dtsession_res

if HAS_PAM_LIBRARY
DTPAMSVCLIB = $(LIBPAMSVC)
else
DTPAMSVCLIB =
endif

dtsession_CFLAGS = -DCDE_INSTALLATION_TOP=\"$(CDE_INSTALLATION_TOP)\" \
          -DCDE_CONFIGURATION_TOP=\"$(CDE_CONFIGURATION_TOP)\" \
	  -Ddtsession

dtsession_SOURCES = SmMain.c SmHelp.c SmGlobals.c SmCommun.c		\
	SmError.c SmProperty.c SmProtocol.c SmSave.c SmScreen.c		\
	SmRestore.c SmUI.c SmWindow.c SmLock.c SrvPalette.c		\
	SrvFile_io.c SmStrDefs.c SmConMgmt.c SmXSMP.c SmAuth.c		\
	SmWatch.c SmProp.c SmDB.c OWsync.h SmGlobals.h SmProperty.h	\
	SmScreen.h SmXSMP.h SmAuth.h Sm.h SmProp.h SmUI.h		\
	SrvFile_io.h SmCommun.h SmHelp.h SmProtocol.h SmWatch.h Srv.h	\
	SmConMgmt.h SmHftRing.h SmResource.h SmWindow.h SrvPalette.h	\
	SmDB.h SmLock.h SmRestore.h SmXdef.h SmError.h			\
	SmMigResources.h SmSave.h SmXrm.h


dtsession_LDADD = $(DTCLIENTLIBS) $(XTOOLLIB) $(DTPAMSVCLIB) $(TIRPCLIB)

if SOLARIS
dtsession_SOURCES += OWsync.c
dtsession_LDADD += -lelf
endif

if LINUX
dtsession_CFLAGS += -DUSE_X11SSEXT
dtsession_LDADD += -lXss
endif

if BSD
dtsession_CFLAGS += -DUSE_X11SSEXT
dtsession_LDADD +=  -lXss
endif

SUBDIRS = config

CLEANFILES = Dtsession dtsession_res dtsession.msg sys.font	\
	sys.resources sys.session

# systems without a PAM library need dtsession to be SUID root

install-exec-hook:
if !HAS_PAM_LIBRARY
	chown root $(DESTDIR)$(bindir)/dtsession
	chmod 4755 $(DESTDIR)$(bindir)/dtsession
endif

