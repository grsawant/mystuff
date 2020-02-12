# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $

COMMENT =	C++ library for resampling audio signals

V =		1.6.2
DISTNAME =	zita-resampler-${V}

SHARED_LIBS =	zita-resampler		0.0 # 0.0

CATEGORIES =	audio

HOMEPAGE =	https://kokkinizita.linuxaudio.org/linuxaudio/

MAINTAINER =		Dimitri Karamazov <deserter666@danwin1210.me>

#GPLv3
PERMIT_PACKAGE =	Yes

WANTLIB += ${COMPILER_LIBCXX} m
COMPILER = base-clang ports-gcc

MASTER_SITES =		${HOMEPAGE}/downloads/
EXTRACT_SUFX =		.tar.bz2

BUILD_DEPENDS =		audio/libsndfile

WRKSRC =		${WRKDIST}/source

CONFIGURE_STYLE =	none

MAKE_ENV =		LMAJ=${LIBzita-resampler_VERSION:R} \
			LMIN=${LIBzita-resampler_VERSION:E}
FAKE_FLAGS =		DESTDIR=
ALL_TARGET =

NO_TEST =		Yes

.include <bsd.port.mk>
