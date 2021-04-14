## Process this file with automake to produce Makefile.in.

## Copyright (C) 2021 Mark J. Wielaard <mark@klomp.org>
##
## This program is free software: you can redistribute it and/or modify
## it under the terms of the GNU General Public License as published by
## the Free Software Foundation; either version 3 of the License, or
## (at your option) any later version.
##
## This program is distributed in the hope that it will be useful,
## but WITHOUT ANY WARRANTY; without even the implied warranty of
## MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
## GNU General Public License for more details.
##
## You should have received a copy of the GNU General Public License
## along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Tests have their own directory and Makefile.am everything else is
# defined here.
SUBDIRS = tests

AM_CFLAGS = -Wall

# All our programs
bin_PROGRAMS = debugedit sepdebugcrcfix

# Install find-debuginfo.sh in $(bindir) and distribute it.
dist_bin_SCRIPTS = scripts/find-debuginfo.sh

debugedit_SOURCES = tools/debugedit.c \
		    tools/hashtab.c \
		    tools/md5.c \
		    tools/sha1.c
debugedit_CFLAGS = @LIBELF_CFLAGS@ @LIBDW_CFLAGS@ $(AM_CFLAGS)
debugedit_LDADD = @LIBELF_LIBS@ @LIBDW_LIBS@

sepdebugcrcfix_SOURCES = tools/sepdebugcrcfix.c
sepdebugcrcfix_CFLAGS = @LIBELF_CFLAGS@ $(AM_CFLAGS)
sepdebugcrcfix_LDADD = @LIBELF_LIBS@

noinst_HEADERS= tools/ansidecl.h \
		tools/hashtab.h \
		tools/md5.h \
		tools/sha1.h

EXTRA_DIST = README COPYING COPYING3 COPYING.LIB