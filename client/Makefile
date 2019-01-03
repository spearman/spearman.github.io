PANDOC_STRING = pandoc -s --ascii --toc --toc-depth=6 --number-sections -f markdown -t html

index: foo
	$(PANDOC_STRING) $@ -o $@.html

.PHONY: foo
%: foo html/
	$(PANDOC_STRING) $@ -o html/$@.html

# dummy rule to prevent Makefile from trying to make itself
Makefile: ;

html/:
	mkdir -p html/

clean:
	rm html/*.html
	rm index.html
