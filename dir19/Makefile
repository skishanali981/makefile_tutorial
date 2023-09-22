nullstring =
foo = $(nullstring) 
nullstring = not null
all:
ifeq ($(strip $(foo)),)
	echo "foo is empty after stripping"
else
	echo "foo has been changes after modifying nullstring"
endif



ifeq ($(nullstring),)
	echo "nullstring does not have spaces"
else
	echo "nullstring has been changes after modifying foo"
endif
