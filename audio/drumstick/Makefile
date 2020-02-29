# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $

COMMENT =	MIDI libraries for Qt5/C++

V =		1.1.3
DISTNAME =	drumstick-${V}

SHARED_LIBS +=	drumstick-file	0.0 # 0.0
SHARED_LIBS +=	drumstick-rt	0.0 # 0.0

CATEGORIES =	audio

HOMEPAGE =	http://drumstick.sourceforge.net/

MAINTAINER =		Gagandeep Sawant <grsa32@gmail.com>

#GPLv2
PERMIT_PACKAGE =	Yes

WANTLIB += ${COMPILER_LIBCXX} Qt5Core Qt5Gui Qt5Network Qt5Svg
WANTLIB += Qt5Widgets c curses fluidsynth m pulse pulse-simple
WANTLIB += readline

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=drumstick/1.1.3/}
EXTRACT_SUFX =		.tar.bz2

MODULES =		devel/cmake \
			x11/qt5

RUN_DEPENDS =		devel/desktop-file-utils \
			x11/gtk+3,-guic
LIB_DEPENDS =		audio/fluidsynth \
			audio/pulseaudio \
			x11/qt5/qtsvg

do-patch:
	@sed -ie "s@\(pkg_check_modules(FLUIDSYNTH\).*@\1 fluidsynth)@g" \
	 ${WRKSRC}/library/rt-backends/CMakeLists.txt

.include <bsd.port.mk>
