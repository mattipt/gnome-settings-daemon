NULL =

plugin_name = xsettings

noinst_PROGRAMS = test-gtk-modules

test_gtk_modules_SOURCES =	\
	gsd-xsettings-gtk.c	\
	gsd-xsettings-gtk.h	\
	test-gtk-modules.c

test_gtk_modules_CFLAGS =		\
	$(PLUGIN_CFLAGS)		\
	$(SETTINGS_PLUGIN_CFLAGS)	\
	$(AM_CFLAGS)

test_gtk_modules_LDADD =		\
	$(SETTINGS_PLUGIN_LIBS)

test_gtk_modules_CPPFLAGS =				\
	-I$(top_srcdir)/gnome-settings-daemon		\
	-I$(top_srcdir)/data/				\
	-DGNOME_SETTINGS_LOCALEDIR=\""$(datadir)/locale"\" \
	-DGTK_MODULES_DIRECTORY=\""$(libdir)/gnome-settings-daemon-@GSD_API_VERSION@/gtk-modules/"\" \
	$(AM_CPPFLAGS)

plugin_LTLIBRARIES = \
	libxsettings.la		\
	$(NULL)

libxsettings_la_SOURCES = 	\
	gsd-xsettings-plugin.h	\
	gsd-xsettings-plugin.c	\
	gsd-xsettings-manager.h	\
	gsd-xsettings-manager.c	\
	gsd-xsettings-gtk.c	\
	gsd-xsettings-gtk.h	\
	xsettings-common.h	\
	xsettings-common.c	\
	xsettings-manager.h	\
	xsettings-manager.c	\
	fontconfig-monitor.h	\
	fontconfig-monitor.c	\
	$(NULL)

libxsettings_la_CPPFLAGS = \
	-I$(top_srcdir)/gnome-settings-daemon		\
	-I$(top_srcdir)/data/				\
	-DGNOME_SETTINGS_LOCALEDIR=\""$(datadir)/locale"\" \
	-DGTK_MODULES_DIRECTORY=\""$(libdir)/gnome-settings-daemon-@GSD_API_VERSION@/gtk-modules/"\" \
	$(AM_CPPFLAGS)

libxsettings_la_CFLAGS = \
	$(SETTINGS_PLUGIN_CFLAGS)	\
	$(FONTCONFIG_CFLAGS)		\
	$(AM_CFLAGS)

libxsettings_la_LDFLAGS = 	\
	$(GSD_PLUGIN_LDFLAGS)	\
	$(NULL)

libxsettings_la_LIBADD  = 	\
	$(SETTINGS_PLUGIN_LIBS)	\
	$(FONTCONFIG_LIBS)	\
	$(NULL)

plugin_in_files = 		\
	xsettings.gnome-settings-plugin.in	\
	$(NULL)

plugin_DATA = $(plugin_in_files:.gnome-settings-plugin.in=.gnome-settings-plugin)

EXTRA_DIST = 			\
	$(plugin_in_files)	\
	$(NULL)

CLEANFILES = 			\
	$(plugin_DATA)		\
	$(NULL)

DISTCLEANFILES =		\
	$(plugin_DATA)		\
	$(NULL)

@GSD_INTLTOOL_PLUGIN_RULE@
