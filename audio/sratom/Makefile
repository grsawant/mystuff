# $OpenBSD$

COMMENT=	library for serialising LV2 atoms to/from RDF

V=		0.6.8
DISTNAME=	sratom-${V}

SHARED_LIBS=	sratom-0	0.0 # 0.6

CATEGORIES=	audio

HOMEPAGE=	https://drobilla.net/software/sratom

MAINTAINER=     Gagandeep Sawant <grsa32@gmail.com>

# MIT
PERMIT_PACKAGE= Yes

WANTLIB += m serd-0 sord-0

MASTER_SITES=	http://download.drobilla.net/

EXTRACT_SUFX=	.tar.bz2

MODULES=	lang/python

BUILD_DEPENDS=	audio/lv2

LIB_DEPENDS=	devel/serd \
		devel/sord

RUN_DEPENDS=	audio/lv2

# requires library gcov
NO_TEST=	Yes

do-configure:
	cd ${WRKSRC} && env -i ${CONFIGURE_ENV} \
	    ${MODPY_BIN} ./waf configure \
		--prefix=${PREFIX} \
		--mandir=${PREFIX}/man

do-build:
	cd ${WRKSRC} && env -i ${MAKE_ENV} ${MODPY_BIN} ./waf -v

do-install:
	cd ${WRKSRC} && env -i ${MAKE_ENV} ${MODPY_BIN} ./waf install \
		--destdir=${DESTDIR}

.include <bsd.port.mk>
