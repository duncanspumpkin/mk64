CC := gcc
CFLAGS := -I . -Wall -Wextra -Wno-unused-parameter -pedantic -std=c99 -O2 -s
PROGRAMS := mio0 n64graphics n64cksum tkmk00


n64graphics_SOURCES := n64graphics.c utils.c
n64graphics_CFLAGS  := -DN64GRAPHICS_STANDALONE

mio0_SOURCES := libmio0.c
mio0_CFLAGS := -DMIO0_STANDALONE

tkmk00_SOURCES := libtkmk00.c utils.c
tkmk00_CFLAGS := -DTKMK00_STANDALONE

n64cksum_SOURCES := n64cksum.c utils.c
n64cksum_CFLAGS := -DN64CKSUM_STANDALONE

all: $(PROGRAMS)

clean:
	$(RM) $(PROGRAMS)

define COMPILE =
$(1): $($1_SOURCES)
	$(CC) $(CFLAGS) $($1_CFLAGS) $$^ -o $$@
endef

$(foreach p,$(PROGRAMS),$(eval $(call COMPILE,$(p))))
