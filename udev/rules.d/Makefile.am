udevrule_DATA = \
	69-vdev.rules \
	60-zvol.rules \
	90-zfs.rules

EXTRA_DIST = \
	69-vdev.rules.in \
	60-zvol.rules.in \
	90-zfs.rules.in

$(udevrule_DATA):%:%.in
	-$(SED) -e 's,@bindir\@,$(bindir),g' \
		-e 's,@sbindir\@,$(sbindir),g' \
		-e 's,@udevdir\@,$(udevdir),g' \
		-e 's,@udevruledir\@,$(udevruledir),g' \
		-e 's,@sysconfdir\@,$(sysconfdir),g' \
		$< > '$@'

# Double-colon rules are allowed; there are multiple independent definitions.
distclean-local::
	-$(RM) $(udevrule_DATA)
