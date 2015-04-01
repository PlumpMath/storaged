
NULL =

man_MANS =

if ENABLE_MAN
notrans_man_MANS = \
	@STORAGED_EXEC_NAME@.8 \
	$(NULL)
endif

storaged.xml: storaged.xml.in
	@sed -e "s|\@storagedexecname\@|$(STORAGED_EXEC_NAME)|" $< > $@

@STORAGED_EXEC_NAME@.8 : storaged.xml
	$(XSLTPROC) -path "$(builddir)/.." -nonet http://docbook.sourceforge.net/release/xsl/current/manpages/docbook.xsl $<

EXTRA_DIST= \
	storaged.xml.in \
	$(NULL)

clean-local:
	rm -f *~ *.[18]
	rm -f *.xml
