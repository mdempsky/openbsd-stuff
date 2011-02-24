# Needs working fenv.h.
ONLY_FOR_ARCHES =	amd64 i386 sparc64

COMMENT =		Computational Geometry Algorithms Library

V =			3.7
PKGNAME =		cgal-${V}
DISTNAME =		CGAL-${V}

SHARED_LIBS =		CGAL		0.0 \
			CGAL_Core	0.0 \
			CGAL_ImageIO	0.0 \
			CGAL_Qt4	0.0 

CATEGORIES =		math

# mix of LGPLv2.1 and QPL; see http://www.cgal.org/license.html
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

WANTLIB =		GL GLU ICE SM X11 Xext boost_thread-mt gmp gmpxx \
			lib/qt4/QtGui lib/qt4/QtOpenGL m mpfr stdc++ z

# Awkward hosting site; see https://gforge.inria.fr/frs/?group_id=52 for files index.
MASTER_SITES =		https://gforge.inria.fr/frs/download.php/27641/

MODULES =		devel/cmake \
			x11/qt4
LIB_DEPENDS =		devel/boost \
			devel/gmp \
			devel/mpfr

CONFIGURE_ENV =         CFLAGS="${CFLAGS} -I${X11BASE}/include" \
                        CXXFLAGS="${CXXFLAGS} -I${X11BASE}/include" \
                        LDFLAGS="${LDFLAGS} -L${X11BASE}/lib"

.include <bsd.port.mk>
