# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $

COMMENT =	a music creation tool intended for live use

GH_ACCOUNT =	openAVproductions
GH_PROJECT =	openAV-Luppp
GH_TAGNAME =	release-1.2.1

CATEGORIES =	audio

HOMEPAGE =	http://openavproductions.com/luppp/

MAINTAINER =		Dimitri Karamazov <deserter666@danwin1210.me

#GPLv2
PERMIT_PACKAGE =	Yes

WANTLIB = 	X11 c c++ c++abi cairo jack lo m samplerate sndfile ntk

COMPILER = base-clang ports-gcc

MODULES =		devel/meson
LIB_DEPENDS =		audio/jack \
			audio/liblo \
			x11/ntk
RUN_DEPENDS =		devel/desktop-file-utils

.include <bsd.port.mk>
