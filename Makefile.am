SUBDIRS      = .
AM_CFLAGS    = -I$(top_srcdir)

bin_PROGRAMS = uemacs

uemacs_SOURCES =	\
	ansi.c		\
	basic.c		\
	bind.c		\
	buffer.c	\
	crypt.c		\
	display.c	\
	eval.c exec.c	\
	file.c		\
	fileio.c	\
	ibmpc.c		\
	input.c		\
	isearch.c	\
	line.c		\
	lock.c		\
	main.c		\
	pklock.c	\
	posix.c		\
	random.c	\
	region.c	\
	search.c	\
	spawn.c		\
	tcap.c		\
	termio.c	\
	vmsvt.c		\
	vt52.c		\
	window.c	\
	word.c		\
	names.c		\
	globals.c	\
	version.c	\
	usage.c		\
	wrapper.c	\
	utf8.c

uemacs_CFLAGS =		\
	-DAUTOCONF -DPOSIX -DUSG -D_DEFAULT_SOURCE -D_XOPEN_SOURCE=600 \
	-DDATADIR=\"$(datadir)/uemacs/\"

uemacs_LDADD = 	\
	-lncurses

uemacs.manifest: uemacs.manifest.in
	cat $< | sed 's#@__BINDIR__@#$(bindir)#g' > $@

install-data-hook:
	$(MKDIR_P) $(DESTDIR)$(datadir)/uemacs && \
		cp $(top_srcdir)/emacs.hlp $(DESTDIR)$(datadir)/uemacs && \
		cp $(top_srcdir)/emacs.rc $(DESTDIR)$(datadir)/uemacs/.emacsrc
