MAITAINERCLEANFILES = Makefile.in

bin_PROGRAMS = dtspcd

dtspcd_CFLAGS = -DCDE_CONFIGURATION_TOP=\"${prefix}\" \
		-DCDE_INSTALLATION_TOP=\"$(CDE_INSTALLATION_TOP)\" \
		$(DT_INCDIR)

dtspcd_LDADD = $(DTCLIENTLIBS) $(XTOOLLIB)

if SOLARIS
dtspcd_LDADD += -lgen
endif

cfgdir = $(CDE_INSTALLATION_TOP)/config
dist_cfg_DATA = dtspcdenv

# I really think we should get rid of dtspcd in general...

dtspcd_SOURCES = main.c spcd_event.c

CPP_TARGETS = dtspcdenv
CLEANFILES = $(CPP_TARGETS)
