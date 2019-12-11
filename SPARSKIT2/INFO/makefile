ifdef ARCH

  include ../make.$(ARCH)

else
  # 
  F77 = gfortran
  #F77 = cf77
  FFLAGS = -g -Wall 
endif

FILES = rinfo1.o dinfo13.o
## needs library libskit.a in whatever machine version: 
##LIB   = -L/project/darpa/lib/solaris -lskit
LIB   = -L./../ -lskit

%.o : %.f
	$(F77) $(FFLAGS) -o $@ -c $<

info1.ex: $(FILES) 
	$(F77) $(FFLAGS) -o info1.ex $(FILES) $(LIB) 

clean:
	rm -f *.o *.L *.LL *.ex core *.trace *~ 

.f.o  : ;       $(F77) $(FFLAGS) -c $*.f -o $*.o
