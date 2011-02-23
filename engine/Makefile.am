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

engine_table_PYTHON = \
	factory.py \
	main.py \
	indic_table.py \
	tabcreatedb.py \
	tabdict.py \
	tabsqlitedb.py \
	$(NULL)
engine_table_DATA = \
	$(NULL)
engine_tabledir = $(datadir)/ibus-indic-table/engine

bin_SCRIPTS = ibus-indic-table-createdb 

libexec_SCRIPTS = ibus-engine-indic-table

engine_DATA = indic-table.xml
enginedir = $(datadir)/ibus/component

EXTRA_DIST = \
	ibus-indic-table-createdb.in \
	ibus-engine-indic-table.in \
	indic-table.xml.in \
	$(NULL)

CLEANFILES = \
	*.pyc \
	*.pyo \
	ibus-engine-indic-table \
	ibus-indic-table-createdb \
	indic-table.xml \
	$(NULL)

MAINTAINERCLEANFILES = \
	Makefile.in \
	$(NULL)

indic-table.xml: indic-table.xml.in
	( \
		libexecdir=${libexecdir}; \
		pkgdatadir=${pkgdatadir}; \
		s=`cat $<`; \
		eval "echo \"$${s}\""; \
	) > $@

test:
	$(ENV) \
		IBUS_INDIC_TABLE_LOCATION=$(abs_top_srcdir) \
		DBUS_DEBUG=true \
		LANG=en_US \
		PYTHONPATH=$(abs_top_srcdir) \
		$(PYTHON) $(srcdir)/main.py

