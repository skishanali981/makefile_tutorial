new_contents= "hello:\n\techo \$$(cooly)"

cooly = "The sub-directory can see me"
export cooly
all:
	mkdir -p subdir
	#printf $(new_contents) | sed -e 's/^ //' > subdir/Makefile
	printf $(new_contents) > subdir/Makefile
	@echo "--Makefile Contents---"
	@cd subdir && cat Makefile
	@echo "---END MAKEFILE CONTENTS---"
	cd subdir && $(MAKE)


clean:
	rm -rf subdir
