FFLAGS = -O2
F77 = gfortran

#F77 = cf77
#FFLAGS = -Wf"-dp"

FILES1 = rsobel.o
FILES2 = rzlatev.o
FILES3 = markov.o

ALL: sobel.ex zlatev.ex markov.ex

%.o : %.f
	$(F77) $(FFLAGS) -o $@ -c $<

sobel.ex:	$(FILES1) ../../libskit.a 
	$(F77) $(FFLAGS) -o sobel.ex $(FILES1)  ../../libskit.a 

zlatev.ex:	$(FILES2) ../../libskit.a 
	$(F77) $(FFLAGS) -o zlatev.ex $(FILES2)  ../../libskit.a 

markov.ex:	$(FILES3) ../../libskit.a 
	$(F77) $(FFLAGS) -o markov.ex $(FILES3)  ../../libskit.a 

clean:
	rm -f *.o *.ex core *.trace

../../libskit.a:
	(cd ../..; $(MAKE) $(MAKEFLAGS) libskit.a)

