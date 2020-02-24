# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $
COMMENT =	See more with less

DISTNAME =	lesspipe-1.84

GH_ACCOUNT =	wofr06
GH_PROJECT =	lesspipe
GH_TAGNAME =	1.84

CATEGORIES =	textproc

HOMEPAGE =	https://www-zeuthen.desy.de/~friebel/unix/lesspipe.html

MAINTAINER =	Gagandeep Sawant <grsa32@gmail.com>

#GPLv2
PERMIT_PACKAGE =	Yes

BUILD_DEPENDS =		shells/bash

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/lesspipe.sh ${PREFIX}/bin
	${INSTALL_SCRIPT} ${WRKSRC}/code2color ${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/lesspipe.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
