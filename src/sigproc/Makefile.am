AM_CFLAGS = $(all_includes) -I$(top_srcdir)/include $(FFTW_CFLAGS) -Wall -std=c99 -march=native -g

noinst_LTLIBRARIES = libsigproc.la

libsigproc_la_SOURCES = \
	sigvec.c \
	fft.c \
	interpolate.c \
	correlate.c \
	convert.c

if ARCH_ARM
libsigproc_la_SOURCES += \
	convolve_neon.c \
	conv_neon.S \
	sigvec_neon.c \
	mul4_neon.S \
	mul4_const_neon.S \
	mac4_neon.S \
	mac4_conj_neon.S \
	norm4_neon.S
else
libsigproc_la_SOURCES += convolve_sse.c
endif
