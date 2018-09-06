# GNU Makefile

OUTPUTFILE = libapp_sup.a
CLEANEXTS = o a
CC = gcc
CFLAGS += -I../../include -DLINUX_POWERPC

#.PHONY: all
#all: $(OUTPUTFILE)

# Build static library
$(OUTPUTFILE): app_pnic.o app_xmal.o rmalloc.o
	#ar -r -o $@ $^
	#gcc $(CFLAGS) $^ -o $@
	ar ru $@ $^
	ranlib $@

# app_pnic.o: app_pnic.c
# 	gcc -c $(CFLAGS) -o $@ $<

# app_xmal.o: app_xmal.c
# 	gcc -c $(CFLAGS) -o $@ $<

# rmalloc.o: rmalloc.c
# 	gcc -c $(CFLAGS) -o $@ $<

# Enumerating of every .c to .o
%.o: %.c
	$(CC) -c $(CFLAGS) -o $@ $<

.PHONY: clean
clean:
	for file in $(CLEANEXTS); do rm -f *.$$file; done