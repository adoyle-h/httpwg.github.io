saxpath ?= "lib/saxon9.jar"
saxon ?= java -classpath $(saxpath) net.sf.saxon.Transform -l
saxparam ?= bootstrapJsUrl='../bower_components/bootstrap/dist/js/bootstrap.min.js' \
					  bootstrapCssUrl='../bower_components/bootstrap/dist/css/bootstrap.min.css' \
						jqueryJsUrl='../bower_components/jquery/dist/jquery.min.js' \
						siteCssUrl='../asset/site.css' \
						navbar='../../_includes/navbar.html'
saxparamZH ?= bootstrapJsUrl='../../bower_components/bootstrap/dist/js/bootstrap.min.js' \
					  bootstrapCssUrl='../../bower_components/bootstrap/dist/css/bootstrap.min.css' \
						jqueryJsUrl='../../bower_components/jquery/dist/jquery.min.js' \
						siteCssUrl='../../asset/site.css' \
						navbar='../../_includes/navbar.html'
stylesheet := lib/rfcbootstrap.xslt
specs := $(subst .xml,,$(wildcard rfc*.xml))
TARGETS := $(addsuffix .html,$(specs))
Lang := zh-Hans
FOLDER := $(Lang)
zhFiles := $(subst rfc,zh,$(specs))

.PHONY: all clean zh $(zhFiles)

all: $(TARGETS) zh

clean:
	@rm -f po/*.mo; \
	rm -f *-$(Lang).xml; \
	rm -f $(FOLDER)/*; \
	echo done;

$(zhFiles): zh%: $(FOLDER)/rfc%.html

zh: $(foreach filename,$(specs),$(Lang)/$(filename).html)

%.html: %.xml $(stylesheet)
	$(saxon) $< $(stylesheet) $(saxparam) > $@

$(FOLDER)/%.html: %-$(Lang).xml $(stylesheet)
	$(saxon) $< $(stylesheet) $(saxparamZH) > $@

%-$(Lang).xml: $(FOLDER) po/%.mo %.xml
	itstool -k -m po/$*.mo $*.xml -o $*-$(Lang).xml

$(FOLDER):
	mkdir -p $(FOLDER)

po/%.mo: po/%.po
	msgfmt po/$*.po -o $@

po/%.po: po
	itstool -k $*.xml -o $@

$(subst rfc,po,$(specs)): po%: po/rfc%.po

po:
	mkdir -p po

