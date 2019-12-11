ifdef ARCH

  include ../make.$(ARCH)

  FFLAGS += -DUNIX -g

else

  FFLAGS = -DUNIX -O3 -g 
  F77 = gfortran

endif

LINK = -L ../. -lskit

ALL: mvec.ex tester.ex

%.o : %.f
	$(F77) $(FFLAGS) -o $@ -c $<

mvec.ex: rmatvec.o ../MATGEN/FDIF/functns.o ../libskit.a
	$(F77) $(FFLAGS) -o mvec.ex rmatvec.o ../MATGEN/FDIF/functns.o $(LINK)

tester.ex: tester.o ../MATGEN/FDIF/functns.o 
	$(F77) $(FFLAGS) -o tester.ex tester.o ../MATGEN/FDIF/functns.o $(LINK)
clean:
	rm -f *.o *.L *.LL *.ex core *.trace fort.* ftn??

../MATGEN/FDIF/functns.o:
	(cd ../MATGEN/FDIF; $(F77) $(FFLAGS) -c functns.f)

../libskit.a:
	(cd ..; $(MAKE) $(MAKEFLAGS) libskit.a)

