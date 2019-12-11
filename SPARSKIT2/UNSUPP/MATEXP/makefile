ifdef ARCH

  include ../../make.$(ARCH)

else
  FFLAGS = -O2
  F77 = gfortran
endif

FILES1 = rexp.o exppro.o 
FILES2 = rphi.o phipro.o 

ALL: exp.ex phi.ex

%.o : %.f
	$(F77) $((FFLAGS) -o $@ -c $<

exp.ex:		$(FILES1)
	$(F77) $(FFLAGS) $(FILES1) -o exp.ex  

phi.ex:		$(FILES2)
	$(F77) $(FFLAGS) $(FILES2) -o phi.ex  

clean:
	rm -f *.o *.L *.LL *.ex core *.trace

