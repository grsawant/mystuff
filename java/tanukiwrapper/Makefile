# $OpenBSD$

COMMENT=	Tanuki Java Service Wrapper

DISTNAME=	wrapper_3.5.43_src
PKGNAME=	java-tanukiwrapper-3.5.43
CATEGORIES=	java

HOMEPAGE=	http://wrapper.tanukisoftware.com/

MAINTAINER=	Gagandeep Sawant <grsa32@gmail.com>

MASTER_SITES=	https://download.tanukisoftware.com/wrapper/3.5.43/

# GPLv2
PERMIT_PACKAGE=	Yes

MODULES=	java
MODJAVA_VER=	1.8
MODJAVA_BUILD=	ant

.include <bsd.port.arch.mk>
.if ${PROPERTIES:Mlp64}
BITS=64
.else
BITS=32
.endif

MODJAVA_BUILD_ARGS= -Dbits=${BITS}

WANTLIB=	c iconv m pthread

LIB_DEPENDS=	converters/libiconv

USE_GMAKE=	Yes

SUBST_VARS+=	CC CFLAGS

post-extract:
	cp ${FILESDIR}/Makefile-openbsd-x86-${BITS}.gmake ${WRKSRC}/src/c/

pre-configure:
	${SUBST_CMD} ${WRKSRC}/src/c/Makefile-openbsd-x86-${BITS}.gmake

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/java/classes/  \
		${PREFIX}/lib/tanukuwrapper/
	${INSTALL_DATA} ${WRKSRC}/lib/wrapper.jar \
		${PREFIX}/share/java/classes/tanukiwrapper.jar
	${INSTALL_PROGRAM} ${WRKSRC}/lib/libwrapper.so ${PREFIX}/lib/tanukuwrapper/
	${INSTALL_PROGRAM} ${WRKSRC}/bin/wrapper ${PREFIX}/sbin/tanukiwrapper

do-test:
	cd ${WRKSRC} && ant -Dbits=${BITS} -f build-tests.xml

.include <bsd.port.mk>
