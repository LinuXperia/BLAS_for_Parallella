#  
#  -- High Performance Computing Linpack Benchmark (HPL)                
#     HPL - 2.1 - October 26, 2012                          
#     Antoine P. Petitet                                                
#     University of Tennessee, Knoxville                                
#     Innovative Computing Laboratory                                 
#     (C) Copyright 2000-2008 All Rights Reserved                       
#                                                                       
#  -- Copyright notice and Licensing terms:                             
#                                                                       
#  Redistribution  and  use in  source and binary forms, with or without
#  modification, are  permitted provided  that the following  conditions
#  are met:                                                             
#                                                                       
#  1. Redistributions  of  source  code  must retain the above copyright
#  notice, this list of conditions and the following disclaimer.        
#                                                                       
#  2. Redistributions in binary form must reproduce  the above copyright
#  notice, this list of conditions,  and the following disclaimer in the
#  documentation and/or other materials provided with the distribution. 
#                                                                       
#  3. All  advertising  materials  mentioning  features  or  use of this
#  software must display the following acknowledgement:                 
#  This  product  includes  software  developed  at  the  University  of
#  Tennessee, Knoxville, Innovative Computing Laboratory.             
#                                                                       
#  4. The name of the  University,  the name of the  Laboratory,  or the
#  names  of  its  contributors  may  not  be used to endorse or promote
#  products  derived   from   this  software  without  specific  written
#  permission.                                                          
#                                                                       
#  -- Disclaimer:                                                       
#                                                                       
#  THIS  SOFTWARE  IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
#  ``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES,  INCLUDING,  BUT NOT
#  LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
#  A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE UNIVERSITY
#  OR  CONTRIBUTORS  BE  LIABLE FOR ANY  DIRECT,  INDIRECT,  INCIDENTAL,
#  SPECIAL,  EXEMPLARY,  OR  CONSEQUENTIAL DAMAGES  (INCLUDING,  BUT NOT
#  LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
#  DATA OR PROFITS; OR BUSINESS INTERRUPTION)  HOWEVER CAUSED AND ON ANY
#  THEORY OF LIABILITY, WHETHER IN CONTRACT,  STRICT LIABILITY,  OR TORT
#  (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
#  OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE. 
# ######################################################################
#  
include Make.inc
#
# ######################################################################
#
INCdep           = \
   $(INCdir)/hpl_misc.h  $(INCdir)/hpl_pmisc.h  $(INCdir)/hpl_grid.h
#
## Object files ########################################################
#
HPL_griobj       = \
   HPL_grid_init.o        HPL_pnum.o             HPL_grid_info.o        \
   HPL_grid_exit.o        HPL_broadcast.o        HPL_reduce.o           \
   HPL_all_reduce.o       HPL_barrier.o          HPL_min.o              \
   HPL_max.o              HPL_sum.o
#
## Targets #############################################################
#
all     : lib 
#
lib     : lib.grd
#
lib.grd : $(HPL_griobj)
	$(ARCHIVER) $(ARFLAGS) $(HPLlib) $(HPL_griobj)
	$(RANLIB) $(HPLlib)
	$(TOUCH) lib.grd
#
# ######################################################################
#
HPL_grid_init.o        : ../HPL_grid_init.c        $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_grid_init.c
HPL_pnum.o             : ../HPL_pnum.c             $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_pnum.c
HPL_grid_info.o        : ../HPL_grid_info.c        $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_grid_info.c
HPL_grid_exit.o        : ../HPL_grid_exit.c        $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_grid_exit.c
HPL_broadcast.o        : ../HPL_broadcast.c        $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_broadcast.c
HPL_reduce.o           : ../HPL_reduce.c           $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_reduce.c
HPL_all_reduce.o       : ../HPL_all_reduce.c       $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_all_reduce.c
HPL_barrier.o          : ../HPL_barrier.c          $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_barrier.c
HPL_min.o              : ../HPL_min.c              $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_min.c
HPL_max.o              : ../HPL_max.c              $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_max.c
HPL_sum.o              : ../HPL_sum.c              $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_sum.c
#
# ######################################################################
#
clean            :
	$(RM) *.o *.grd
#
# ######################################################################
