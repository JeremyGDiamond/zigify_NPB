SHELL=/bin/sh
CLASS=S
SFILE=config/suite.def

default: header
	@ $(SHELL) sys/print_instructions

BT: bt
bt: header
	mkdir -p bin
	cd BT; $(MAKE) CLASS=$(CLASS)
		       
SP: sp		       
sp: header	       
	mkdir -p bin
	cd SP; $(MAKE) CLASS=$(CLASS)
		       
LU: lu		       
lu: header	       
	mkdir -p bin
	cd LU; $(MAKE) CLASS=$(CLASS)
		       
MG: mg		       
mg: header	       
	mkdir -p bin
	cd MG; $(MAKE) CLASS=$(CLASS)
		       
FT: ft		       
ft: header	       
	mkdir -p bin
	cd FT; $(MAKE) CLASS=$(CLASS)
		       
IS: is		       
is: header	       
	mkdir -p bin
	cd IS; $(MAKE) CLASS=$(CLASS)
		       
CG: cg		       
cg: header	       
	mkdir -p bin
	cd CG; $(MAKE) CLASS=$(CLASS)
		       
EP: ep		       
ep: header	       
	mkdir -p bin
	cd EP; $(MAKE) CLASS=$(CLASS)

# Awk script courtesy cmg@cray.com
suite:
	@ awk '{ if ($$1 !~ /^#/ &&  NF > 0)                              \
	printf "make %s CLASS=%s\n", $$1, $$2 }' $(SFILE)  \
	| $(SHELL)


# It would be nice to make clean in each subdirectory (the targets
# are defined) but on a really clean system this will won't work
# because those makefiles need config/make.def
clean:
	- rm -f core 
	- rm -f *~ */core */*~ */*.o */npbparams.h */*.obj */*.exe
	- rm -f sys/setparams sys/makesuite sys/setparams.h

veryclean: clean
	- rm config/make.def config/suite.def Part*
	- rm bin/sp.* bin/lu.* bin/mg.* bin/ft.* bin/bt.* bin/is.* bin/ep.* bin/cg.*

header:
	@ $(SHELL) sys/print_header

kit: 
	- makekit -s100k -k30 * */* */*/*


