dnl Run autoreconf --install to generate ./configure from this file
AC_INIT([agan8021xclient], [1.2], [agan8021xclient-bugs@lists.sourceforge.net], [], [http://sourceforge.net/projects/agan8021xclient/])
AM_INIT_AUTOMAKE([-Wall -Werror foreign])
AC_PROG_CC


dnl -----------------------------------------------------------------
dnl pcap check
AC_MSG_CHECKING(["whether to use libpcap for packet capture"])

AC_ARG_WITH([pcap],
  AC_HELP_STRING( [--with-pcap@<:@=DIR@:>@],
                  [use libpcap for packet capturing @<:@default=yes@:>@]),
[
	if test $withval = no
	then
		want_pcap=no
	elif test $withval = yes
	then
		want_pcap=yes
	else
		want_pcap=yes
		pcap_dir=$withval
	fi
],[
	want_pcap=yes
	pcap_dir=
])
if test "x$want_pcap" = "xno" ; then
	AC_MSG_RESULT(no)
else
	AC_MSG_RESULT(yes)
	AC_WIRESHARK_PCAP_CHECK
fi
dnl -----------------------------------------------------------------



PKG_CHECK_MODULES([libcrypto], [libcrypto])
AC_CONFIG_HEADER([config.h])
AC_CONFIG_FILES([Makefile])
AC_OUTPUT

