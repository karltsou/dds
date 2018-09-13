# GNU Makefile

OUTPUTFILE = libcm.a
CLEANEXTS = o a
CC = gcc
CFLAGS += -I../../include -DLINUX_POWERPC
CFLAGS += -I/usr/lib/gcc/x86_64-linux-gnu/4.8/include
src = $(wildcard *.c)
obj = $(src:.c=.o)

# Build static library
$(OUTPUTFILE): $(obj)
	#ar -r -o $@ $^
	#gcc $(CFLAGS) $^ -o $@
	ar ru $@ $^
	ranlib $@

# include dep files
-include $(dep)
# rule to generate a dep file
%.d: %.c
	@$(CC) $(CFLAGS) $< -MM -MT $(@:.d=.o) >$@

.PHONY: clean
clean:
	for file in $(CLEANEXTS); do rm -f *.$$file; done