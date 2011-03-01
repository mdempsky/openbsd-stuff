# $OpenBSD$

COMMENT =		libactp

V = 			44
DISTNAME =		libactp-${V}

CATEGORIES =		cad

HOMEPAGE =		http://code.google.com/p/libactp/

# mix of GPLv2+ and GPLv3
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

WANTLIB =		m stdc++ util
WANTLIB +=		${MODPY_WANTLIB}

WRKSRC =		${WRKDIST}/PythonLib

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
