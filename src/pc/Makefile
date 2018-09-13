# GNU Makefile

OUTPUTFILE = libpc.a
CLEANEXTS = o a
CC = gcc
CFLAGS += -I../../include
src = $(wildcard *.c)
obj = $(src:.c=.o)

# Build static library
$(OUTPUTFILE): pc.o
	#ar -r -o $@ $^
	#gcc $(CFLAGS) $^ -o $@
	ar ru $@ $^
	ranlib $@

# include dep files
-include $(dep)
# rule to generate a dep file
%.d: %.c
	@$(CC) $(CFLAGS) $< -MM -MT $(@:.d=.o) >$

.PHONY: clean
clean:
	for file in $(CLEANEXTS); do rm -f *.$$file; done