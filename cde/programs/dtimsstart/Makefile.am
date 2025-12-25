cfgdir = $(CDE_INSTALLATION_TOP)/config/Xsession.d

MAINTAINERCLEANFILES = Makefile.in

bin_PROGRAMS = dtimsstart

dist_cfg_SCRIPTS = 0020.dtims

dtimsstart_CFLAGS = -DNLS 

dtimsstart_LDADD = $(DTCLIENTLIBS) $(XTOOLLIB)

dtimsstart_SOURCES = action.c env.c file.c main.c remote.c select.c	\
		     start.c util.c win.c ximserr.h ximsfunc.h xims.h	\
		     ximspath.h

CLEANFILE = 0020.dtims

imsdir = $(CDE_INSTALLATION_TOP)/config/ims
dist_ims_DATA = conf/start.conf
