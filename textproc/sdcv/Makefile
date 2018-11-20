# $OpenBSD: Makefile,v 1.78 2018/07/09 15:00:06 jca Exp $

COMMENT =	command-line dictionary lookup tool

VERSION =	0.5.2
DISTNAME =	sdcv-${VERSION}

GH_ACCOUNT =	Dushistov
GH_PROJECT =	sdcv
GH_TAGNAME =	v${VERSION}

CATEGORIES =	textproc

HOMEPAGE =	https://dushistov.github.io/sdcv/

MAINTAINER = 	Nikita Frolov <nf@mkmks.org>

# GPL2
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c glib-2.0 intl m readline z
COMPILER =		ports-gcc
MODULES =		devel/cmake
BUILD_DEPENDS =		devel/gettext-tools
LIB_DEPENDS =		devel/glib2 \
			devel/gettext

post-patch:
.for i in doc/sdcv.1 src/sdcv.cpp
	@sed -i 's|/usr/share|${PREFIX}/share|' ${WRKSRC}/${i}
.endfor
	@sed -i 's|share/man|man|' ${WRKSRC}/CMakeLists.txt

post-build:
	cd ${WRKBUILD} && ${NINJA} lang

.include <bsd.port.mk>
