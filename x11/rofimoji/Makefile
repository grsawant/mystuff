# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $
COMMENT =	character picker for rofi

GH_ACCOUNT =	fdw
GH_PROJECT =	rofimoji
GH_TAGNAME =	4.2.0

CATEGORIES =	x11
HOMEPAGE =	https://www.google.com/get/noto/

MAINTAINER =		Dimitri Karamazov <deserter666@danwin1210.me>

#MIT
PERMIT_PACKAGE =	Yes

MODULES =		lang/python
MODPY_SETUPTOOLS =	Yes
MODPY_VERSION =		${MODPY_DEFAULT_VERSION_3}

LIB_DEPENDS =		devel/py-configargparse${MODPY_FLAVOR} \
			devel/py-xdg${MODPY_FLAVOR}
RUN_DEPENDS =		x11/xdotool \
			x11/xsel \
			sysutils/rofi

NO_TEST =		Yes

.include <bsd.port.mk>
