# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $

COMMENT =	simple and fast file manager

GH_ACCOUNT =	dylanaraps
GH_PROJECT =	fff
GH_TAGNAME =	2.1

CATEGORIES =	sysutils

MAINTAINER =		Dimitri Karamazov <deserter666@danwin1210.me>

#MIT
PERMIT_PACKAGE =	Yes

RUN_DEPENDS =		converters/libiconv \
			devel/gettext,-runtime \
			devel/xdg-utils \
			shells/bash

NO_BUILD =		Yes
NO_TEST =		Yes

FAKE_FLAGS = DESTDIR= MANDIR=${DESTDIR}${PREFIX}/man

.include <bsd.port.mk>
