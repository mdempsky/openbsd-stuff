# XXX: Depends on libgomp in base.

COMMENT =		open 3d cam path library

V =			679
DISTNAME =		opencamlib-${V}

SHARED_LIBS =		ocl	0.0

CATEGORIES =		cad

HOMEPAGE =		http://code.google.com/p/opencamlib/

# GPLv3+
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

WANTLIB =		boost_python-mt gomp m pthread stdc++

# XXX; svn only

WRKSRC =		${WRKDIST}/src

CONFIGURE_ARGS =	-DBUILD_CXX_LIB=ON \
			-DBUILD_DOC=ON

MODULES =		devel/cmake \
			lang/python
LIB_DEPENDS =		devel/boost

pre-configure:
	ln -sf ${LOCALBASE}/bin/python2.6 ${WRKDIR}/bin/python
	ln -sf ${LOCALBASE}/bin/python2.6-config ${WRKDIR}/bin/python-config

.include <bsd.port.mk>
