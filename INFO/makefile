ifdef ARCH

  include ../make.$(ARCH)

else
  # 
  F77 = gfortran
  FFLAGS = -g -Wall 
endif

FILES = rinfo1.o dinfo13.o

LIB   = -L./../ -lskit

%.o : %.f
	$(F77) $(FFLAGS) -o $@ -c $<

info1.ex: $(FILES) 
	$(F77) $(FFLAGS) -o info1.ex $(FILES) $(LIB) 

clean:
	rm -f *.o *.L *.LL *.ex core *.trace *~ 

