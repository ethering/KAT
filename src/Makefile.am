AUTOMAKE_OPTIONS = subdir-objects


# What to build
bin_PROGRAMS = kat

# Executable inputs
kat_CXXFLAGS = \
	-fwrapv -Wall -m64 \
	-Wno-deprecated-declarations -Wno-unused-function -Wno-unused-parameter \
	-Wno-unused-variable -Wno-unused-command-line-argument \
	@AM_CXXFLAGS@

kat_CPPFLAGS = \
	-I$(top_srcdir)/deps/seqan-library-2.0.0/include \
	-I$(top_srcdir)/deps/jellyfish-2.2.0/include \
	-I$(top_srcdir)/deps/boost/build/include \
	-I$(top_srcdir)/lib/include \
	-DKAT_SCRIPTS='"$(datadir)/kat/scripts"' \
	-DKAT_EXECPREFIX='"$(exec_prefix)"' \
	@AM_CPPFLAGS@

kat_LDFLAGS = \
	-static \
	@AM_LDFLAGS@

kat_LDADD = \
	$(top_builddir)/deps/boost/build/lib/libboost_timer.a \
	$(top_builddir)/deps/boost/build/lib/libboost_chrono.a \
	$(top_builddir)/deps/boost/build/lib/libboost_filesystem.a \
	$(top_builddir)/deps/boost/build/lib/libboost_program_options.a \
	$(top_builddir)/deps/boost/build/lib/libboost_system.a \
	$(top_builddir)/deps/jellyfish-2.2.0/.libs/libkat_jellyfish.la \
	$(top_builddir)/lib/libkat.la \
	@AM_LIBS@

noinst_HEADERS = \
	plot.hpp \
	filter_kmer.hpp \
	filter_sequence.hpp \
	filter.hpp \
	comp.hpp \
	gcp.hpp \
	histogram.hpp \
	sect.hpp \
        cold.hpp

kat_SOURCES = \
	plot.cc \
	filter_kmer.cc \
	filter_sequence.cc \
	filter.cc \
	comp.cc \
	gcp.cc \
	histogram.cc \
	sect.cc \
        cold.cc \
	kat.cc
