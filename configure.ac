dnl Process this file with autoconf to produce a configure script.
AC_PREREQ(2.59)
AC_INIT([e2tools], [0.0.16.3], [hun@n-dimensional.de], [e2tools])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_HEADER([config.h])
AC_CONFIG_SRCDIR([e2tools.c])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([-Wall -Werror 1.9.6 dist-bzip2])

dnl Checks for programs.
AC_PROG_CC
gl_EARLY
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET

dnl Checks for libraries.
gl_INIT
PKG_CHECK_MODULES([EXT2FS], [ext2fs >= 1.27], [], [
    AC_MSG_ERROR([Sorry, but we do require libext2fs.])])
PKG_CHECK_MODULES([COM_ERR], [com_err], [], [
    AC_MSG_ERROR([Sorry, but we do require libcom_err.])])

dnl Checks for header files.
AC_HEADER_STDC
AC_CHECK_HEADERS(errno.h fcntl.h sys/time.h unistd.h)

dnl Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST
AC_TYPE_MODE_T
AC_TYPE_OFF_T
AC_TYPE_UINT8_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT64_T
AC_TYPE_INT8_T
AC_TYPE_INT16_T
AC_TYPE_INT32_T
AC_TYPE_INT64_T
AC_HEADER_TIME
AC_STRUCT_TM

dnl Checks for library functions.
AC_FUNC_ALLOCA
AC_FUNC_UTIME_NULL
AC_CHECK_FUNCS(gettimeofday regcomp strdup strtol)

CFLAGS="$CFLAGS -Wall"
LDFLAGS="$LDFLAGS -pthread"

AC_CONFIG_FILES([
    Makefile
    lib/Makefile
])
AC_OUTPUT
