CC = gcc
CFLAGS = -Wall -Wconversion -O3

LIBS = -lm
EXEC = sandbox
TEST = test
INC_DIR = ../Core/Inc
SRC_DIR = ../Core/Src

OBJS = ece5210.o
INCS = ece5210.h

all: $(TEST) $(EXEC)

$(EXEC): sandbox.o $(OBJS)
	$(CC) -o $@ $^ $(LIBS)

$(TEST): unittests.o $(OBJS)
	$(CC) -o $@ $^ $(LIBS)

sandbox.o: sandbox.c $(INC_DIR)/$(INCS)
	$(CC) -c -o $@ $< $(CFLAGS) -I $(INC_DIR)

unittests.o: unittests.c $(INC_DIR)/$(INCS)
	$(CC) -c -o $@ $< $(CFLAGS) -I $(INC_DIR)

ece5210.o: $(SRC_DIR)/ece5210.c $(INC_DIR)/$(INCS)
	$(CC) -c -o $@ $< $(CFLAGS) -I $(INC_DIR)

.PHONY: clean
clean:
	rm -f sandbox.o debug.o unittests.o $(OBJS) $(EXEC) $(TEST) *~* *.mtx *.dSYM *.out 
