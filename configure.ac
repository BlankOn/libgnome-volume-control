#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([libgnome-volume-control],[0.1],[blankon-dev@googlegroups.com])
AC_CONFIG_SRCDIR([src/gvc-mixer-control-private.h])
AC_CONFIG_HEADERS([config.h])
AM_INIT_AUTOMAKE([dist-bzip2])

# Checks for programs.
AC_PROG_CC
AC_PROG_LIBTOOL
LT_PREREQ([2.2.6])
LT_INIT([disable-static])

IT_PROG_INTLTOOL([0.40])

GETTEXT_PACKAGE=libgnome-volume-control
AC_SUBST(GETTEXT_PACKAGE)
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE, "$GETTEXT_PACKAGE", [The prefix for our gettext translation domains.])

# Checks for libraries.

# Checks for header files.
AC_CHECK_HEADERS([stdlib.h string.h unistd.h])
AC_DEFINE_UNQUOTED(HAVE_INSTROPECTION, "$PWD/system", [Location of the JS scripts])
AC_SUBST(SYSTEM_PATH)

GOBJECT_INTROSPECTION_MIN_VERSION=0.10.1
GOBJECT_INTROSPECTION_CHECK([$GOBJECT_INTROSPECTION_MIN_VERSION])

# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_UINT32_T

# Checks for library functions.
AC_CHECK_FUNCS([memset strstr])

PKG_CHECK_MODULES(GVC, glib-2.0 >= 2.12 libpulse-mainloop-glib >= 4.0 libpulse >= 4.0)
AC_SUBST(GVC_CFLAGS)
AC_SUBST(GVC_LIBS)

AC_CONFIG_FILES([Makefile src/Makefile po/Makefile.in])
AC_OUTPUT
