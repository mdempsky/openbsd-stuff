# $OpenBSD$

COMMENT =		libarea

V = 			83
DISTNAME =		libarea-${V}

CATEGORIES =		cad

HOMEPAGE =		http://code.google.com/p/libactp/

# mix of GPLv3, 3-clause BSD, and Boost (MIT-like)
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

WANTLIB =		boost_python m stdc++ util
WANTLIB +=		${MODPY_WANTLIB}

USE_GMAKE =		Yes

MODULES =		lang/python
LIB_DEPENDS =		devel/boost

CONFIGURE_STYLE =	none

MAKE_ENV =		CFLAGS="-I${LOCALBASE}/include" \
			CXXFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"

pre-configure:
	ln -sf ${MODPY_BIN} ${WRKDIR}/bin/python
	ln -sf ${MODPY_BIN}-config ${WRKDIR}/bin/python-config

.include <bsd.port.mk>
