# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $

COMMENT=	tools for storage and manipulation of volumetric data

GH_ACCOUNT=	dreamworksanimation
GH_PROJECT=	openvdb
GH_TAGNAME=	v7.1.0

SHARED_LIBS +=  openvdb                   0.0 # 7.1

CATEGORIES=	graphics

HOMEPAGE=	https://www.openvdb.org/

MAINTAINER=	Dimitri Karamazov <deserter666@danwin1210.me>

# MPL
PERMIT_PACKAGE=	Yes

WANTLIB +=	${COMPILER_LIBCXX} Half-2_5 blosc boost_iostreams-mt
WANTLIB +=	boost_regex-mt boost_system-mt c m tbb tbbmalloc z

COMPILER=	base-clang ports-gcc base-gcc

MODULES=	devel/cmake

LIB_DEPENDS=	archivers/blosc \
		devel/boost \
		devel/tbb \
		graphics/openexr

NO_TEST=	Yes

.include <bsd.port.mk>
