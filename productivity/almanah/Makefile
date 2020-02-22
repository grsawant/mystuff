# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $

COMMENT =	small gtk+2 application to keep a diary

GNOME_PROJECT =	almanah
GNOME_VERSION =	0.12.0
EXTRACT_SUFX =	.tar.xz

CATEGORIES =	productivity

HOMEPAGE =	https://wiki.gnome.org/Apps/Almanah_Diary

MAINTAINER =		Gagandeep Sawant <grsa32@gmail.com>

#GPL
PERMIT_PACKAGE =	Yes

WANTLIB += atk-1.0 c cairo cryptui ecal-2.0 edataserver-1.2 gcr-base-3
WANTLIB += gdk-3 gio-2.0 glib-2.0 gobject-2.0 gpgme gtk-3 gtksourceview-3.0
WANTLIB += gtkspell3-3 ical-glib intl pango-1.0 pangocairo-1.0
WANTLIB += sqlite3

MODULES =		devel/dconf \
			devel/meson \
			x11/gnome

BUILD_DEPENDS =		devel/gettext,-tools

LIB_DEPENDS =		databases/evolution-data-server \
			textproc/gtkspell3 \
			x11/gnome/libcryptui \
			x11/gtksourceview3

RUN_DEPENDS =		devel/desktop-file-utils \
			x11/gtk+3,-guic

NO_TEST =	Yes

.include <bsd.port.mk>
