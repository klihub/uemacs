#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([FULL-PACKAGE-NAME], [VERSION], [BUG-REPORT-ADDRESS])

AC_CONFIG_SRCDIR([.])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_HEADERS([config.h])

# Automake
AM_INIT_AUTOMAKE([-Wno-portability subdir-objects foreign])
AC_SUBST(ACLOCAL_AMFLAGS, "-I m4")

# Checks for programs.
AC_PROG_CC
AC_PROG_CC_C99
AC_PROG_AWK
AC_PROG_INSTALL
AM_PROG_CC_C_O
AM_PROG_LIBTOOL

# Checks for libraries.
# FIXME: Replace `main' with a function in `-lcurses':
AC_CHECK_LIB([curses], [initscr])

# Checks for header files.
AC_CHECK_HEADERS([fcntl.h memory.h sgtty.h stdlib.h string.h strings.h sys/ioctl.h sys/systeminfo.h termio.h termios.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_INLINE
AC_TYPE_SIZE_T

# Checks for library functions.
AC_FUNC_LSTAT_FOLLOWS_SLASHED_SYMLINK
AC_FUNC_MALLOC
AC_CHECK_FUNCS([gethostname memmove strerror sysinfo])

# Which IoT user to install under, if any.
AC_ARG_WITH(iot-user,
            [  --with-iot-user          IoT user name],
            [iotusr="$with_iot_user"], [iotusr=__none__])

if test "$iotusr" != "__none__"; then
    IOT_USER="$iotusr"
else
    IOT_USER=""
fi

IOT_MANIFEST_DIR="/usr/share/iot/users"

AC_SUBST(IOT_USER)
AC_SUBST(IOT_MANIFEST_DIR)


# Shave by default.
SHAVE_INIT([build-aux], [enable])

AC_CONFIG_FILES([build-aux/shave
                 build-aux/shave-libtool
                 Makefile
                ])
AC_OUTPUT
