CC      = /usr/bin/gcc
SRCS    = bad_getenv_demo.c getenv_demo.c getpid_demo.c gettid_demo.c hello.c \
          hello_world.c stdin_demo.c
BUILDDIR = ../build/chapter01
PROGRAMS = $(patsubst %.c,%,$(SRCS))
OBJS    = $(patsubst %.c,$(BUILDDIR)/%.o,$(SRCS))
EXECS   = $(addprefix $(BUILDDIR)/,$(PROGRAMS))
CFLAGS  = -Wall -g 
MAKEFLAGS += -k

.PHONY: all clean cleanall $(PROGRAMS)

all: $(EXECS)

$(PROGRAMS): %: $(BUILDDIR)/%

clean:
	-rm -f $(OBJS)

cleanall:
	-rm -f $(OBJS) $(EXECS)

$(BUILDDIR)/%: %.c
	mkdir -p $(BUILDDIR)
	$(CC) $(CFLAGS) $< $(LDFLAGS) -o $@
