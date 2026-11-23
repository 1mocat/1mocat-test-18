# Modernized Makefile for gfortran
FC = gfortran
FFLAGS = -I. -fopenmp -O2
LDFLAGS = -fopenmp

SRCDIR = src
TARGET_EXEC = test_program
OBJS_LIB = my_lib.o
OBJS_MAIN = test_main.o
OBJS = $(OBJS_LIB) $(OBJS_MAIN)

.PHONY: all clean

all: $(TARGET_EXEC)

$(TARGET_EXEC): $(OBJS)
	$(FC) $(FFLAGS) -o $(TARGET_EXEC) $(OBJS) $(LDFLAGS)

my_lib.o: $(SRCDIR)/my_lib.f90
	$(FC) $(FFLAGS) -c $(SRCDIR)/my_lib.f90 -o my_lib.o

test_main.o: $(SRCDIR)/test_main.f90 $(SRCDIR)/my_lib.f90
	$(FC) $(FFLAGS) -c $(SRCDIR)/test_main.f90 -o test_main.o

clean:
	rm -f $(TARGET_EXEC) $(OBJS) output.txt *.mod
