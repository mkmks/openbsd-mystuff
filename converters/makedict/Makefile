# $OpenBSD: Makefile,v 1.78 2018/07/09 15:00:06 jca Exp $

COMMENT =	multiformat dictionary converter

VERSION =	33
DISTNAME =	makedict-${VERSION}

GH_ACCOUNT =	soshial
GH_PROJECT =	xdxf_makedict
GH_TAGNAME =	rev${VERSION}

CATEGORIES =	converters

HOMEPAGE =	https://github.com/soshial/xdxf_makedict

MAINTAINER = 	Nikita Frolov <nf@mkmks.org>

# GPL2
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c expat glib-2.0 iconv intl m z
WANTLIB += 		${COMPILER_LIBCXX}
MODULES =		devel/cmake \
			lang/python
LIB_DEPENDS =		devel/glib2 \
			devel/gettext
post-patch:
	@sed -i 's|share/man|man|' ${WRKSRC}/CMakeLists.txt

post-install:
	${MODPY_BIN} ${MODPY_LIBDIR}/compileall.py ${PREFIX}/lib/makedict-codecs/

.include <bsd.port.mk>
