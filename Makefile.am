pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = wayland-egl.pc

AM_CFLAGS = $(DEFINES) \
	    $(VISIBILITY_CFLAGS) \
	    $(WAYLAND_CFLAGS)

ACLOCAL_AMFLAGS = -I m4

lib_LTLIBRARIES = libwayland-egl.la
noinst_HEADERS = wayland-egl-priv.h
libwayland_egl_la_SOURCES = wayland-egl.c
libwayland_egl_la_LDFLAGS = \
	-no-undefined \
	-version-info 1 \
	$(GC_SECTIONS) \
	$(LD_NO_UNDEFINED)

TESTS = wayland-egl-symbols-check
EXTRA_DIST = wayland-egl-symbols-check

libwayland_egl_la_CFLAGS = \
	@WAYLAND_CLIENT_CFLAGS@

libwayland_egl_la_LIBADD = \
	@WAYLAND_CLIENT_LIBS@
