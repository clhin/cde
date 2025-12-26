MAINTAINERCLEANFILES = Makefile.in

bin_PROGRAMS = dtstyle

dtstyle_CPPFLAGS = -DCDE_CONFIGURATION_TOP=\"$(CDE_CONFIGURATION_TOP)\"	\
	-DCDE_INSTALLATION_TOP=\"$(CDE_INSTALLATION_TOP)\" -I../dthelp	\
	$(DT_INCDIR)

dtstyle_LDADD = $(DTCLIENTLIBS) $(XTOOLLIB)

dtstyle_SOURCES = Main.c MainWin.c Font.c Audio.c Startup.c Mouse.c	\
		  SaveRestore.c Backdrop.c Screen.c Keyboard.c		\
		  ColorMain.c ColorPalette.c ColorFile.c ColorEdit.c	\
		  Resource.c Protocol.c Dtwm.c Help.c HelpCB.c		\
		  I18nMain.c I18nEnv.c I18nUtil.c Audio.h ColorMain.h	\
		  Help.h Keyboard.h OWsync.h Screen.h Backdrop.h	\
		  ColorPalette.h I18nEnv.h Main.h Protocol.h		\
		  Startup.h ColorEdit.h Dtwm.h I18nMain.h MainWin.h	\
		  Resource.h ColorFile.h Font.h I18nUtil.h Mouse.h	\
		  SaveRestore.h

if SOLARIS
dtstyle_SOURCES += OWsync.c
endif

appdefaultsdir = $(CDE_CONFIGURATION_TOP)/app-defaults/C

dist_appdefaults_DATA = Dtstyle

CPP_TARGETS = Dtstyle Backdrops Palettes

CLEANFILES = $(CPP_TARGETS)
