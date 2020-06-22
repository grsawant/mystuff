# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $

COMMENT =	stream based reader and writer library for COLLADA files

V =		1.6.68
GH_ACCOUNT =	KhronosGroup
GH_PROJECT =	OpenCOLLADA
GH_TAGNAME =	v${V}
DISTNAME =	${GH_PROJECT:L}-${V}

SHARED_LIBS +=  GeneratedSaxParser		0.0
SHARED_LIBS +=  MathMLSolver			0.0
SHARED_LIBS +=	OpenCOLLADABaseUtils		0.0
SHARED_LIBS +=	OpenCOLLADAFramework		0.0
SHARED_LIBS +=	OpenCOLLADASaxFrameworkLoader	0.0
SHARED_LIBS +=	OpenCOLLADAStreamWriter		0.0
SHARED_LIBS +=	UTF				0.0
SHARED_LIBS +=	buffer				0.0
SHARED_LIBS +=  ftoa				0.0
SHARED_LIBS +=	zlib				0.0

CATEGORIES =	graphics

MAINTAINER =	Dimitri Karamazov <deserter666@danwin1210.me>

# MIT
PERMIT_PACKAGE =Yes

WANTLIB += ${COMPILER_LIBCXX} m pcre pcreposix xml2

COMPILER =	base-clang ports-gcc base-gcc

MODULES =	devel/cmake

LIB_DEPENDS =	devel/pcre \
		textproc/libxml

CONFIGURE_ARGS =-DOPENCOLLADA_INST_LIBRARY=${LOCALBASE}/lib \
		-DOPENCOLLADA_INST_CMAKECONFIG=${LOCALBASE}/lib/cmake/opencollada \
		-DUSE_SHARED=ON

NO_TEST =	Yes

.include <bsd.port.mk>
