#==============================================================================
#
# Makefile for JCSDA CRTM Example/Test programs
#
# $Id:$
#
#==============================================================================

include ../../../make.macros

# The executable and object files
EXE_FILE = Example1_Simple
SRC_FILE = $(EXE_FILE).f90
OBJ_FILE = ${SRC_FILE:.f90=.o}

EXTRA_FC_FLAGS = -I../../../$(INC_DIR)
LIBRARIES = -L../../../$(LIB_DIR) -l$(PACKAGE)

all: $(OBJ_FILE)
	@echo; echo; \
	echo "=============================================="; \
	echo "Building k_matrix $(EXE_FILE) using:"; \
	echo "  Compiler: $(FC)"; \
	echo "  Switches: $(FC_FLAGS)"; \
	echo "=============================================="; \
	$(FL) $(OBJ_FILE) $(FL_FLAGS) $(LIBRARIES) -o $(EXE_FILE)

clean:
	@echo; echo; \
	echo "=============================================="; \
	echo "Cleaning up k_matrix $(EXE_FILE)"; \
	echo "=============================================="; \
	$(REMOVE) $(OBJ_FILE) $(EXE_FILE) gmon.out *.output results/*.signal
        
update:
	@echo; echo; \
	echo "=============================================="; \
	echo "Updating results for forward $(EXE_FILE)"; \
	echo "=============================================="; \
	$(MOVE) *.bin    results; \
	$(MOVE) *.output results        

# Local dependencies
$(OBJ_FILE): $(SRC_FILE)

include ../../../make.rules
