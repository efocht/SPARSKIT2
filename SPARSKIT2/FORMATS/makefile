ifdef ARCH

  include ../make.$(ARCH)

else
  FFLAGS =
  F77 = gfortran
endif	

FILES1 = chkun.o
FILES2 = chkfmt1.o 
FILES3 = rvbr.o

ALL: un.ex fmt.ex rvbr.ex

%.o : %.f
	$(F77) $(FFLAGS) -o $@ -c $<

un.ex:	$(FILES1) ../MATGEN/FDIF/functns.o ../libskit.a 
	$(F77) $(FFLAGS) -o un.ex $(FILES1) ../MATGEN/FDIF/functns.o ../libskit.a 

fmt.ex:	$(FILES2) ../MATGEN/FDIF/functns.o ../libskit.a 
	$(F77) $(FFLAGS) -o fmt.ex $(FILES2) ../MATGEN/FDIF/functns.o ../libskit.a 

rvbr.ex: $(FILES3) ../MATGEN/FDIF/functns.o ../libskit.a 
	$(F77) $(FFLAGS) -o rvbr.ex $(FILES3) ../MATGEN/FDIF/functns.o ../libskit.a

clean:
	rm -f *.o *.L *.LL *.ex core *.trace

../MATGEN/FDIF/functns.o:
	(cd ../MATGEN/FDIF; $(F77) $(FFLAGS) -c functns.f)

../libskit.a:
	(cd ..; $(MAKE) $(MAKEFLAGS) libskit.a)

