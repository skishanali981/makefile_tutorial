obj_files = foo.result bar.o lose.o
src_files = foo.raw bar.c lose.c

all: $(obj_files)

.PHONY: all

$(filter %.o,$(obj_files)): %.o:%.c
	echo "target: $@ prereq $<"


$(filter %.result,$(obj_files)): %.result: %.raw
	echo "target: $@ prereq $<"

%.c %.raw:
	touch $@

clean:
	rm -rf $(src_files)
