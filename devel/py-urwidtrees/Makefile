# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $

COMMENT =	tree widgets for urwid

MODPY_EGG_VERSION =	1.0.3
DISTNAME =	urwidtrees-${MODPY_EGG_VERSION}
PKGNAME =	py-${DISTNAME}

CATEGORIES =	devel

HOMEPAGE =	https://github.com/pazz/urwidtrees

MAINTAINER =		Gagandeep Sawant <grsa32@gmail.com>

#GPLv3
PERMIT_PACKAGE =	Yes

MODULES =		lang/python
MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes
MODPY_VERSION =		${MODPY_DEFAULT_VERSION_3}

LIB_DEPENDS =		devel/py-urwid${MODPY_FLAVOR}

FLAVORS =	python3
FLAVOR ?=	python3

.include <bsd.port.mk>
