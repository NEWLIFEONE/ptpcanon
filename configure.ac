# Process this file with autoconf to produce a configure script.
AC_PREREQ(2.53)
AC_INIT([ptpcanon],[0.0.3],[nikolai.kopanygin@gmail.com])
AM_INIT_AUTOMAKE
AM_CONFIG_HEADER([config.h])
AC_PROG_LIBTOOL

# library versioning
# (quoted from libtool doc)
# 1. Update the version information only immediately before a public release
# 2. If the library source code has changed at all since the last update,
#    then increment revision (`c:r:a' becomes `c:r+1:a').
# 3. If any interfaces have been added, removed, or changed since the last
#    update, increment current, and set revision to 0.
# 4. If any interfaces have been added since the last public release,
#    then increment age.
# 5. If any interfaces have been removed since the last public release,
#    then set age to 0. 

CANON_VERSION_CURRENT=0
CANON_VERSION_REVISION=0
CANON_VERSION_AGE=3
CANON_VERSION_INFO=$CANON_VERSION_CURRENT:$CANON_VERSION_REVISION:$CANON_VERSION_AGE
AC_SUBST(CANON_VERSION_INFO)

# Checks for programs.
AC_PROG_CC

# Checks for libraries.

# Checks for header files.
AC_HEADER_STDC
AC_CHECK_HEADERS([libintl.h stdlib.h string.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST
AC_C_INLINE
AC_STRUCT_TM

# Checks for library functions.
AC_FUNC_ERROR_AT_LINE
AC_FUNC_MALLOC
AC_FUNC_MKTIME
AC_FUNC_VPRINTF
AC_CHECK_FUNCS([memset strchr strdup strtol getopt_long])


# Check for libusb
if test "$build_ptpcam" = "yes"
then
	AC_PATH_PROG(LIBUSB_CONFIG,libusb-config)
	if test -n "${LIBUSB_CONFIG}"; then
		AC_CHECK_LIB(usb,usb_busses,
			[LIBUSB_VER="`$LIBUSB_CONFIG --version`"],
			[AC_ERROR([
*** You need at least version 0.1.6 of the libusb library to build ptpcam.
*** Download and istall it from http://sourceforge.net/projects/libusb/ or
*** use --disable-ptpcam option to build without ptpcam tool.
			])])
	fi
	
	if test "$LIBUSB_VER" \< "0.1.6"; then
		AC_ERROR([
*** You need at least version 0.1.6 of the libusb library to build ptpcam.
*** Download and istall it from http://sourceforge.net/projects/libusb/ or
*** use --disable-ptpcam option to build without ptpcam tool.
		])
	fi
fi

AC_CONFIG_FILES([ 
Makefile
])
AC_OUTPUT
