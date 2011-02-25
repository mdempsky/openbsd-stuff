# XXX: libraries aren't being properly handled by cmake.

COMMENT =		HeeksCAD

V =			1432
DISTNAME =		HeeksCAD-${V}
PKGNAME =		heekscad-${V}

SHARED_LIBS =		heeksintf 0.0 \
			sketchsolve 0.0 \
			tinyxml 0.0

CATEGORIES =		cad

# GPLv?
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes


# "make port-lib-depends-check" can help
WANTLIB = FWOSPlugin GL GLU TKAdvTools TKBO TKBRep TKBool TKCAF
WANTLIB += TKCDF TKFeat TKFillet TKG2d TKG3d TKGeomAlgo TKGeomBase
WANTLIB += TKHLR TKIGES TKLCAF TKMath TKMesh TKOffset TKPLCAF
WANTLIB += TKPShape TKPrim TKSTEP TKSTEP209 TKSTEPAttr TKSTEPBase
WANTLIB += TKSTL TKService TKShHealing TKShapeSchema TKTopAlgo
WANTLIB += TKV2d TKV3d TKVRML TKXCAF TKXCAFSchema TKXDESTEP TKXSBase
WANTLIB += TKernel c m pthread python2.6 util wx_base wx_gtk2_aui
WANTLIB += wx_gtk2_core wx_gtk2_gl

CONFIGURE_ENV =         CFLAGS="${CFLAGS} -I${X11BASE}/include" \
                        CXXFLAGS="${CXXFLAGS} -I${X11BASE}/include" \
                        LDFLAGS="${LDFLAGS} -L${X11BASE}/lib" \
			LINK="${CXX}" LD="${CXX}"

# XXX: SVN snapshot

MODULES =		devel/cmake lang/python
LIB_DEPENDS =		cad/opencascade x11/wxWidgets devel/boost x11/gtkglext


# Copied from www/chromium, because warnings about #pragma push.
MODULES+=       gcc4
MODGCC4_LANGS = c c++
MODGCC4_ARCHES = i386 amd64
# XXX cheat
COMPILER_VERSION = gcc3



.include <bsd.port.mk>
