# ZIP up everything
# MIT-style license
#

OUTDIR:=.lib

$(OUTDIR):
	@mkdir -p $(OUTDIR)

$(OUTDIR)/%.xcu : %.xcu $(OUTDIR)
	@cp $< $@
$(OUTDIR)/%.png : %.png $(OUTDIR)
	@cp $< $@
$(OUTDIR)/%.xml : %.xml $(OUTDIR)
	@cp $< $@
$(OUTDIR)/%.txt : %.txt $(OUTDIR)
	@cp $< $@
$(OUTDIR)/META-INF/manifest.xml : META-INF/manifest.xml
	@mkdir -p $(OUTDIR)/META-INF && cp META-INF/manifest.xml $(OUTDIR)/META-INF/
$(OUTDIR)/package/libreoffice_facturx_macro.py : package/libreoffice_facturx_macro.py
	@cp -a package $(OUTDIR)/

../factur-x_macro.oxt : $(OUTDIR)/description.xml $(OUTDIR)/icon_16.png $(OUTDIR)/icon_26.png $(OUTDIR)/Addons.xcu $(OUTDIR)/icon_42.png $(OUTDIR)/META-INF/manifest.xml $(OUTDIR)/package/libreoffice_facturx_macro.py
	@cd $(OUTDIR) && zip -r ../../factur-x_macro.oxt * > /dev/null 2>&1
	@echo Packaging factur-x_macro.oxt done

.PHONY all: ../factur-x_macro.oxt

.PHONY clean:
	rm -fr .lib ../factur-x_macro.oxt
