MAINTAINERCLEANFILES = Makefile.in

if HAS_PAM_LIBRARY
CPP_TARGET = dtsession
dist_pam_DATA = $(CPP_TARGET)
if FREEBSD
pamdir = /usr/local/etc/pam.d
else
pamdir = /etc/pam.d
endif
endif

CLEANFILES = $(CPP_TARGET)
