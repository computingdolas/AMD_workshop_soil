if BUILD_MPI
    MAYBE_MPI = epmpi
endif
SUBDIRS = $(MAYBE_MPI)

include $(top_builddir)/config/config.mk
include $(top_builddir)/config/targets.mk

# How to find source files
VPATH = $(srcdir):$(srcdir)/../../common:$(srcdir)/../../../common

AM_LDFLAGS = $(CUDA_LDFLAGS)
AM_CPPFLAGS = $(CUDA_INC)

# What is the destination for programs built from this directory?
serialcudadir = $(bindir)/Serial/CUDA

CXX=g++
CXXLD=$(NVCC)

# What programs should be installed to that destination?
serialcuda_PROGRAMS = BFS

# How to build those programs?
BFS_SOURCES = Graph.cpp \
				main.cpp
BFS_LDADD = BFS.o bfs_kernel.o $(CUDA_LIBS) $(LIBS)
