COMMENT =		libactp

V = 			44
DISTNAME =		libactp-${V}

# for any port that creates shared libraries.
# both libtool and cmake handle this automatically.
# for libtool-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =		???

# the category used in the directory name, /usr/ports/<category>/portname,
# must be included and listed first.
CATEGORIES =		cad

# GPL?
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

WANTLIB += m python2.6 stdc++ util

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
