if HAVE_SYSTEMD
udevrulesdir = $(udevdir)/rules.d
udevrules_DATA = hdapsd.rules
systemdsystemunit_DATA = \
	hdapsd@.service

edit = sed \
	-e 's|@sbindir[@]|$(sbindir)|g'

hdapsd@.service: Makefile
	rm -f $@ $@.tmp
	srcdir=''; \
	  test -f ./$@.in || srcdir=$(srcdir)/; \
	  $(edit) $${srcdir}$@.in >$@.tmp

	mv $@.tmp $@

hdapsd@.service: hdapsd@.service.in

endif

EXTRA_DIST = \
	hdapsd.rules
