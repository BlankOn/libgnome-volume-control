lib_LTLIBRARIES = libgnome-volume-control.la

INTROSPECTION_SCANNER_ARGS = --warn-all

libgnome_volume_control_la_CPPFLAGS =			\
	$(WARN_CFLAGS)			\
	$(GVC_CFLAGS)			\
	-I.			\
	-I../src			\
	-DWITH_INTROSPECTION		\
	-DG_LOG_DOMAIN="\"Gvc\""

libgnome_volume_control_la_gir_sources = 			\
	../src/gvc-mixer-card.h			\
	../src/gvc-mixer-card.c			\
	../src/gvc-mixer-stream.h			\
	../src/gvc-mixer-stream.c			\
	../src/gvc-channel-map.h			\
	../src/gvc-channel-map.c			\
	../src/gvc-mixer-ui-device.h			\
	../src/gvc-mixer-ui-device.c			\
	../src/gvc-mixer-sink.h			\
	../src/gvc-mixer-sink.c			\
	../src/gvc-mixer-source.h			\
	../src/gvc-mixer-source.c			\
	../src/gvc-mixer-sink-input.h			\
	../src/gvc-mixer-sink-input.c			\
	../src/gvc-mixer-source-output.h		\
	../src/gvc-mixer-source-output.c		\
	../src/gvc-mixer-event-role.h			\
	../src/gvc-mixer-event-role.c			\
	../src/gvc-mixer-control.h			\
	../src/gvc-mixer-control.c			\
	$(NULL)

libgnome_volume_control_la_SOURCES =				\
	$(libgnome_volume_control_la_gir_sources)		\
	../src/gvc-mixer-card-private.h		\
	../src/gvc-mixer-stream-private.h		\
	../src/gvc-channel-map-private.h		\
	../src/gvc-mixer-control-private.h		\
	../src/gvc-pulseaudio-fake.h			\
	$(NULL)

libgnome_volume_control_la_LIBADD = 	\
	$(GVC_LIBS)	\
	$(NULL)

if HAVE_INTROSPECTION
include $(INTROSPECTION_MAKEFILE)

Gvc-1.0.gir: libgnome-volume-control.la
Gvc_1_0_gir_INCLUDES = GObject-2.0 Gio-2.0
Gvc_1_0_gir_CFLAGS = $(INCLUDES) -I../src -I. -DWITH_INTROSPECTION
Gvc_1_0_gir_LIBS = libgnome-volume-control.la
Gvc_1_0_gir_FILES = $(libgnome_volume_control_la_gir_sources)
INTROSPECTION_GIRS = Gvc-1.0.gir

typelibdir = $(pkglibdir)
typelib_DATA = $(INTROSPECTION_GIRS:.gir=.typelib)

CLEANFILES = Gvc-1.0.gir $(typelib_DATA)

endif
