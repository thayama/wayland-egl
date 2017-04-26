pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = wayland-egl.pc

AM_CFLAGS = $(DEFINES) \
	    $(VISIBILITY_CFLAGS) \
	    $(WAYLAND_CFLAGS)

ACLOCAL_AMFLAGS = -I m4

lib_LTLIBRARIES = libwayland-egl.la

libwayland_egl_la_SOURCES = wayland-egl.c
libwayland_egl_la_LDFLAGS = -version-info 1

libwayland_egl_la_CFLAGS = \
	@WAYLAND_CLIENT_CFLAGS@

libwayland_egl_la_LIBADD = \
	@WAYLAND_CLIENT_LIBS@
