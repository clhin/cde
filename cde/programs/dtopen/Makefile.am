MAINTAINERCLEANFILES = Makefile.in

dist_bin_SCRIPTS = dtopen

CLEANFILES = dtopen

install-data-hook:
	$(RM) $(DESTDIR)$(bindir)/dtopen_*
	cd $(DESTDIR)$(bindir) && $(LN_S) dtopen dtopen_video
	cd $(DESTDIR)$(bindir) && $(LN_S) dtopen dtopen_image
	cd $(DESTDIR)$(bindir) && $(LN_S) dtopen dtopen_ps
	cd $(DESTDIR)$(bindir) && $(LN_S) dtopen dtopen_pdf
