ifdef ARCH

  include ../../make.$(ARCH)

else
  FFLAGS = 
  F77 = gfortran
endif

ALL: gen5.ex genbl.ex

%.o : %.f
	$(F77) $(FFLAGS) -c $< -o $@

FILES1 = rgen5pt.o functns.o 

gen5.ex:  $(FILES1) ../../libskit.a 
	$(F77) $(FFLAGS) -o gen5.ex $(FILES1) ../../libskit.a 

FILES2 = rgenblk.o functns.o 
genbl.ex:	$(FILES2)  ../../libskit.a 
	$(F77) $(FFLAGS) -o genbl.ex $(FILES2) ../../libskit.a 

clean:
	rm -f *.o *.L *.LL *.ex core *.trace

../../libskit.a:
	(cd ../..; $(MAKE) $(MAKEFLAGS) libskit.a)

