#
#  Copyright 2005 Red Hat, Inc.
#
#  Permission to use, copy, modify, distribute, and sell this software and its
#  documentation for any purpose is hereby granted without fee, provided that
#  the above copyright notice appear in all copies and that both that
#  copyright notice and this permission notice appear in supporting
#  documentation, and that the name of Red Hat not be used in
#  advertising or publicity pertaining to distribution of the software without
#  specific, written prior permission.  Red Hat makes no
#  representations about the suitability of this software for any purpose.  It
#  is provided "as is" without express or implied warranty.
#
#  RED HAT DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE,
#  INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS, IN NO
#  EVENT SHALL RED HAT BE LIABLE FOR ANY SPECIAL, INDIRECT OR
#  CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE,
#  DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER
#  TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR
#  PERFORMANCE OF THIS SOFTWARE.
#

# Initialize Autoconf
AC_PREREQ([2.69])
AC_INIT([libwayland-egl], [17.0.4],
        [https://bugs.freedesktop.org/enter_bug.cgi?product=Mesa])
AC_CONFIG_SRCDIR([Makefile.am])
AC_CONFIG_HEADERS([config.h])

# Initialize Automake
AM_INIT_AUTOMAKE([foreign dist-bzip2])
#AM_MAINTAINER_MODE
AC_CONFIG_MACRO_DIRS([m4])

# Initialize libtool
AC_PROG_LIBTOOL

# Obtain compiler/linker options for dependencies
PKG_CHECK_MODULES([WAYLAND_CLIENT], [wayland-client])

AC_CONFIG_FILES([Makefile wayland-egl.pc])

# Checks for library functions.
AC_FUNC_MALLOC

dnl
dnl Check if linker supports garbage collection
dnl
save_LDFLAGS=$LDFLAGS
LDFLAGS="$LDFLAGS -Wl,--gc-sections"
AC_MSG_CHECKING([whether ld supports --gc-sections])
AC_LINK_IFELSE(
    [AC_LANG_SOURCE([static char UnusedFunc() { return 5; } int main() { return 0;}])],
    [AC_MSG_RESULT([yes])
        GC_SECTIONS="-Wl,--gc-sections";],
    [AC_MSG_RESULT([no])
        GC_SECTIONS="";])
LDFLAGS=$save_LDFLAGS

## Suggested by libtoolize
LT_INIT([disable-static])

AC_OUTPUT
