# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $
COMMENT =	Fork of fltk with additional facilities

DISTNAME =	fltk-1.3.1000
PKGNAME =	${DISTNAME:S/fl/n/}

SHARED_LIBS +=	ntk		0.0 # 1.3
SHARED_LIBS +=	ntk_images	0.0 # 1.3
SHARED_LIBS +=	ntk_gl		0.0 # 1.3

CATEGORIES =	x11

HOMEPAGE =	https://non.tuxfamily.org/wiki/NTK

MAINTAINER =	Gagandeep Sawant <grsa32@gmail.com>

# LGPLv2 with exceptions (see COPYING)
PERMIT_PACKAGE =	Yes

WANTLIB += ${COMPILER_LIBCXX} GL GLU X11 X11-xcb Xau Xdamage Xdmcp
WANTLIB += Xext Xfixes Xft Xrender Xxf86vm c drm expat ffi fontconfig
WANTLIB += freetype intl m pixman-1 xcb xcb-dri2 xcb-glx xcb-render
WANTLIB += xcb-shm z cairo glib-2.0 gobject-2.0 jpeg pcre png

COMPILER = base-clang ports-gcc

LIB_DEPENDS =	devel/glib2 \
		devel/pcre \
		graphics/png \
		graphics/cairo \
		graphics/jpeg

MODULES =	lang/python
MODPY_VERSION =	${MODPY_DEFAULT_VERSION_3}


MASTER_SITES0 =		https://git.tuxfamily.org/non/fltk.git/snapshot/
MASTER_SITES1 =		https://waf.io/

WAF =			${WRKSRC}/waf-2.0.20
DISTFILES =		${DISTNAME}${EXTRACT_SUFX}:0 ${WAF:T}:1
EXTRACT_ONLY =		${DISTNAME}${EXTRACT_SUFX}

CONFIGURE_ARGS =	--enable-gl

MAKE_ENV = 	CPPFLAGS="-I${LOCALBASE}/include -I${X11BASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib -L${X11BASE}/lib" \
		LMAJ="${LIBntk_VERSION:R}" LMIJ="${LIBntk_VERSION:E}"
MAKE_FLAGS =	--destdir="${DESTDIR}"

DO_WAF =	cd ${WRKSRC} && ${SETENV} ${MAKE_ENV} ${MODPY_BIN} \
			${WAF} ${MAKE_FLAGS}

post-patch:
		cp -r ${DISTDIR}/${WAF:T} ${WAF}
		@sed -e "/LIB_DL/d" -e "/run_ldconfig /d" -i ${WRKSRC}/wscript
do-configure:
		${DO_WAF} configure ${CONFIGURE_ARGS}
do-build:
		${DO_WAF} build -v
do-install:
		${DO_WAF} install
		${INSTALL_DATA_DIR} ${PREFIX}/share/examples/ntk
		${INSTALL_DATA}	${WRKSRC}/test/*.fl \
				${PREFIX}/share/examples/ntk

.include <bsd.port.mk>
