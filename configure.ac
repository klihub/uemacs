#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([uemacs], [4.0.15], [BUG-REPORT-ADDRESS])
AC_CONFIG_SRCDIR([basic.c])
AC_CONFIG_HEADERS([config.h])
AM_INIT_AUTOMAKE([-Wno-portability subdir-objects foreign])

# Checks for programs.
AC_PROG_CXX
AC_PROG_AWK
AC_PROG_CC
AC_PROG_MAKE_SET

# Checks for libraries.
# FIXME: Replace `main' with a function in `-lcurses':
AC_CHECK_LIB([curses], [main])

# Checks for header files.
AC_CHECK_HEADERS([fcntl.h memory.h sgtty.h stdlib.h string.h strings.h sys/ioctl.h sys/systeminfo.h termio.h termios.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_INLINE
AC_TYPE_SIZE_T

# Checks for library functions.
AC_FUNC_LSTAT_FOLLOWS_SLASHED_SYMLINK
AC_FUNC_MALLOC
AC_CHECK_FUNCS([gethostname memmove strerror sysinfo])

AC_CONFIG_FILES([Makefile])
AC_OUTPUT
