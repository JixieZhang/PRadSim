# --------------------------------------------------------------
# $Id: GNUmakefile,v 1.02 2010/12/25  HRSMC Exp $
#
# GNUmakefile for HRSMC 
# --------------------------------------------------------------

name := PRadSim
G4TARGET := $(name)
G4EXLIB := true
#show the cmd line
#CPPVERBOSE = 1

ifndef G4INSTALL
  G4INSTALL = ../../../..
endif

.PHONY: all

all: bin 


#add root package
ROOTCFLAGS   := $(shell root-config --cflags)
ROOTLIBS     := $(shell root-config --libs)
ROOTGLIBS    := $(shell root-config --glibs)

CPPFLAGS  += $(ROOTCFLAGS) -std=c++11 -Ithirdparty/include -fPIC
EXTRALIBS += $(ROOTLIBS) 

#using g4 compiling framework
include $(G4INSTALL)/config/binmake.gmk

help:
	@echo G4TARGET=[$(G4TARGET)]
	@echo CPPFLAGS=[$(CPPFLAGS)] 
	@echo objects=[$(objects)]
	@echo LDFLAGS=[$(LDFLAGS)]
	@echo LDLIBS=[$(LDLIBS)]
	@echo G4TMPDIR=[$(G4TMPDIR)]
	@echo FSOURCE=[$(FSOURCE)] 
	@echo FFLAGS=[$(FFLAGS)] 


distclean:
	@make clean
