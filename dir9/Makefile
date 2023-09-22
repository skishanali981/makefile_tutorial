.EXPORT_ALL_VARIABLES:
new_contents = "hello:\n\techo \$$(cooly)"
cooly = "This is visible from sub-directory"

all:
	mkdir -p subdir
	printf $(new_contents) | sed -e 's/^ //' > subdir/Makefile
	@echo "<--Makefile Contents-->"
	@cd subdir && cat Makefile
	@echo "<--END Makefile Contents-->"
	cd subdir && $(MAKE)

clean:
	rm -rf subdir
