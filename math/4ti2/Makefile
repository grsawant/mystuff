# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $

COMMENT =	solve algebraic, geometric, combinatorial problems

V =		1.6.9
GH_ACCOUNT =	4ti2
GH_PROJECT =	4ti2
GH_TAGNAME =	Release_${V:S/./_/g}
DISTNAME =	${GH_PROJECT}-${V}

CATEGORIES =	math

HOMEPAGE =	https://4ti2.github.io/

MAINTAINER =	Gagandeep Sawant <grsa32@gmail.com>

#GPL
PERMIT_PACKAGE =	Yes

SHARED_LIBS +=	4ti2common	0.0 # 0.0
SHARED_LIBS +=	4ti2gmp		0.0 # 0.0
SHARED_LIBS +=	4ti2int32	0.0 # 0.0
SHARED_LIBS +=	4ti2int64	0.0 # 0.0
SHARED_LIBS +=	4ti2util	0.0 # 0.0
SHARED_LIBS +=	zsolve		0.0 # 0.0

WANTLIB += ${COMPILER_LIBCXX} c glpk gmp gmpxx m
COMPILER =	base-clang ports-gcc

LIB_DEPENDS =		devel/glpk \
			devel/gmp,-cxx

AUTOCONF_VERSION = 	2.69
AUTOMAKE_VERSION = 	1.11
USE_GMAKE =		Yes
CONFIGURE_STYLE =	autoreconf
CONFIGURE_ARGS =	--disable-static \
		 	--enable-shared \
			--with-gmp=${LOCALBASE} \
			--with-glpk=${LOCALBASE}
MAKE_FLAGS =		docdir=${PREFIX}/share/doc/4ti2

TEST_FILES = check.template.in checkall.in flavorsum.in ppi/check-ppi.in
TEST_FILES+= ppi/check-ppi reportfailures.in subdirsum.in check.template
TEST_FILES+= subdirsum flavorsum reportfailures

do-test:
	@cd ${WRKSRC}/test && sed -ie "s/bash/sh/" ${TEST_FILES}
	@cd ${WRKSRC} && ${MAKE_PROGRAM} check


.include <bsd.port.mk>
