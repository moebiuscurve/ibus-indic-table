# vim:set noet ts=4
#
# ibus-indic-table - The Tables engine for IBus
#
# Copyright (c) 2011-2012 Naveen Kumar <nav007@gmail.com>
#
# This library is free software; you can redistribute it and/or
# modify it under the terms of the GNU Lesser General Public
# License as published by the Free Software Foundation; either
# version 2.1 of the License, or (at your option) any later version.
#
# This library is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# Lesser General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public
# License along with this library; if not, write to the Free Software
# Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301  USA
#
# $Id: $
#

SUBDIRS = \
	additional \
	$(NULL)

template_DATA = \
	template.txt \
	$(NULL)

tables_DATA =

templatedir = $(datadir)/ibus-indic-table/indic-tables

EXTRA_DIST = \
	template.txt \
	$(NULL)

MAINTAINERCLEANFILES = \
	Makefile.in \
	$(NULL)

install-data-local:
	$(MKDIR_P) $(DESTDIR)$(pkgdatadir)/indic-tables

createdb = \
	$(PYTHON) $(abs_top_srcdir)/engine/tabcreatedb.py

tables_DATA += $(NULL)

tablesdir = $(datadir)/ibus-table/tables

DISTCLEANFILES = \
        *.db \
        $(NULL)

.txt.db:
	$(createdb) -n $@ -s $<
