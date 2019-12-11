ifdef ARCH

  include ../../make.$(ARCH)

else
  FFLAGS = 
  F77 = gfortran
endif

ALL: fem.ex

%.o : %.f
	$(F77) $(FFLAGS) -c $< -o $@

FILES = convdif.o functns2.o

fem.ex:	$(FILES)  ../../UNSUPP/PLOTS/psgrd.o ../../libskit.a 
	$(F77) $(FFLAGS) -o fem.ex $(FILES) ../../UNSUPP/PLOTS/psgrd.o ../../libskit.a 

clean:
	rm -f *.o *.ex *.L *.LL core *.trace

../../libskit.a:
	(cd ../..; $(MAKE) $(MAKEFLAGS) libskit.a)

../../UNSUPP/PLOTS/psgrd.o: ../../UNSUPP/PLOTS/psgrd.f
	(cd ../../UNSUPP/PLOTS; $(F77) $(FFLAGS) -c psgrd.f)

