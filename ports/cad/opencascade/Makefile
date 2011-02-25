# Based loosely on Debian and FreeBSD's OpenCASCADE packages.
#
# XXX: Is my current way of rerunning autotools correct?
#
# XXX: Move the private libraries into a separate subdirectory and
# unversion them like Debian does?
#
# XXX: Split into multiple packages?
#
# XXX: Probably more cleanups to do in post-install.

COMMENT =	Open CASCADE Technology, 3D modeling & numerical simulation

V =			6.3
DISTNAME =		OpenCASCADE${V}.0
PKGNAME =		opencascade-${V}

SHARED_LIBS =	BinLPlugin           0.0 \
		BinPlugin            0.0 \
		BinTObjPlugin        0.0 \
		BinXCAFPlugin        0.0 \
		FWOSPlugin           0.0 \
		PTKernel             0.0 \
		StdLPlugin           0.0 \
		StdPlugin            0.0 \
		TKAdvTools           0.0 \
		TKBO                 0.0 \
		TKBRep               0.0 \
		TKBin                0.0 \
		TKBinL               0.0 \
		TKBinTObj            0.0 \
		TKBinXCAF            0.0 \
		TKBool               0.0 \
		TKCAF                0.0 \
		TKCDF                0.0 \
		TKCDLFront           0.0 \
		TKCPPClient          0.0 \
		TKCPPExt             0.0 \
		TKCPPIntExt          0.0 \
		TKCPPJini            0.0 \
		TKCSFDBSchema        0.0 \
		TKDCAF               0.0 \
		TKDraw               0.0 \
		TKFeat               0.0 \
		TKFillet             0.0 \
		TKG2d                0.0 \
		TKG3d                0.0 \
		TKGeomAlgo           0.0 \
		TKGeomBase           0.0 \
		TKHLR                0.0 \
		TKIDLFront           0.0 \
		TKIGES               0.0 \
		TKLCAF               0.0 \
		TKMath               0.0 \
		TKMesh               0.0 \
		TKMeshVS             0.0 \
		TKNIS                0.0 \
		TKOffset             0.0 \
		TKOpenGl             0.0 \
		TKPCAF               0.0 \
		TKPLCAF              0.0 \
		TKPShape             0.0 \
		TKPrim               0.0 \
		TKSTEP               0.0 \
		TKSTEP209            0.0 \
		TKSTEPAttr           0.0 \
		TKSTEPBase           0.0 \
		TKSTL                0.0 \
		TKService            0.0 \
		TKShHealing          0.0 \
		TKShapeSchema        0.0 \
		TKStdLSchema         0.0 \
		TKStdSchema          0.0 \
		TKTCPPExt            0.0 \
		TKTObj               0.0 \
		TKTObjDRAW           0.0 \
		TKTopAlgo            0.0 \
		TKTopTest            0.0 \
		TKV2d                0.0 \
		TKV3d                0.0 \
		TKVRML               0.0 \
		TKViewerTest         0.0 \
		TKWOK                0.0 \
		TKWOKTcl             0.0 \
		TKXCAF               0.0 \
		TKXCAFSchema         0.0 \
		TKXDEDRAW            0.0 \
		TKXDEIGES            0.0 \
		TKXDESTEP            0.0 \
		TKXMesh              0.0 \
		TKXSBase             0.0 \
		TKXSDRAW             0.0 \
		TKXml                0.0 \
		TKXmlL               0.0 \
		TKXmlTObj            0.0 \
		TKXmlXCAF            0.0 \
		TKernel              0.0 \
		TKjcas               0.0 \
		XCAFPlugin           0.0 \
		XmlLPlugin           0.0 \
		XmlPlugin            0.0 \
		XmlTObjPlugin        0.0 \
		XmlXCAFPlugin        0.0

# XXX: I think these should be unnumbered.
SHARED_LIBS +=	mscmd                0.0 \
		wokcmd               0.0 \
		wokdeliverysteps     0.0 \
		wokdfltsteps         0.0 \
		wokobjssteps         0.0 \
		wokorbixsteps        0.0 \
		woksteps             0.0 \
		woktoolscmd          0.0 \
		wokutilscmd          0.0 \


# the category used in the directory name, /usr/ports/<category>/portname,
# must be included and listed first.
CATEGORIES =		cad

HOMEPAGE =		http://www.opencascade.org/

# XXX; LGPL like license
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

# "make port-lib-depends-check" can help
WANTLIB =  c
WANTLIB += GL GLU ICE SM X11 Xau Xdamage Xdmcp Xext Xfixes Xft
WANTLIB += Xmu Xrender Xss Xt Xxf86vm drm expat fontconfig freetype
WANTLIB += m pthread pthread-stubs stdc++ xcb z
WANTLIB += ${MODTK_WANTLIB}

# XXX
MASTER_SITES =		http://files.opencascade.com/OCC_6.3_release/
DISTFILES =		OpenCASCADE_src.tgz
DIST_SUBDIR =		opencascade-${V}

# XXX
MODULES =		java lang/tcl x11/tk
MODJAVA_VER =		1.7

BUILD_DEPENDS =		${MODTK_BUILD_DEPENDS}
RUN_DEPENDS =		${MODTK_RUN_DEPENDS}
#LIB_DEPENDS =		???

WRKSRC=		${WRKDIST}/ros
USE_LIBTOOL=		Yes

# Mimicking audio/xmms.
CONFIGURE_STYLE=	gnu
AUTOCONF_VERSION =	2.59
AUTOMAKE_VERSION =	1.9

post-patch:
.for autotool in aclocal autoheader automake autoconf
	cd ${WRKSRC} && env AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} ${autotool}
.endfor

CONFIGURE_ARGS=	--with-java-include=${JAVA_HOME}/include		\
		--with-tcl=${MODTCL_LIBDIR}				\
		--with-tk=${MODTK_LIBDIR}				\
		--with-gl-include=${X11BASE}/include			\
		--with-gl-library=${X11BASE}/lib			\
		--with-xmu-include=${X11BASE}/include/X11		\
		--with-xmu-library=${X11BASE}/lib			\
		--enable-production=yes \
		--disable-debug \
		--disable-dependency-tracking \
		--disable-maintainer-mode

# XXX: configure lists these in its output, but I'm not sure if
# they're actually necessary; README.txt doesn't mention them. 
#		--with-x-include=${X11BASE}/include \
#		--with-x-libraries=${X11BASE}/lib \


# XXX: Ubuntu doesn't use these flags, but the FreeBSD port does.
#		--with-stlport-include=${LOCALBASE}/include/stlport	\
#		--with-stlport-libname=stlport_${STL_COMPILER}		\
#		--with-stlport-library=${LOCALBASE}/lib			\
#		--with-dps-include=${LOCALBASE}/include			\
#		--with-dps-library=${LOCALBASE}/lib			\

CONFIGURE_ENV=	CPPFLAGS="${CXXFLAGS} \
		-I${X11BASE}/include -I${LOCALBASE}/include	\
		-I${MODTCL_INCDIR} -I${MODTK_INCDIR}" ARCH=${ARCH} LD=${CXX} \
		LDFLAGS="-L${X11BASE}/lib -L${LOCALBASE}/lib"
# We strip the libs
MAKE_ENV=	INSTALL_STRIP_FLAG=-s OCC_BUILDDIR="${PATCH_WRKSRC}"	\
		OCC_INSTALLDIR="${OCCROOT}" PTHREAD_LIBS="${PTHREAD_LIBS}" \
		LD=${CXX}

# As Debian eloquently put it: "Fix OpenCascade mess"
post-install:
	rm -rf ${PREFIX}/OpenBSD
	rm ${PREFIX}/config.h ${PREFIX}/inc/config.h
	rm ${PREFIX}/inc/arch-6.3.0/Standard_Macro64.hxx.in # XXX: Why??
	rm ${PREFIX}/env_DRAW.sh # XXX: ??
	find ${PREFIX}/inc -name '*.orig' -exec rm {} \;
	${INSTALL_DATA_DIR} ${PREFIX}/include
	mv ${PREFIX}/inc ${PREFIX}/include/opencascade
	${INSTALL_DATA_DIR} ${PREFIX}/share/opencascade/${V}.0
	mv ${PREFIX}/src ${PREFIX}/share/opencascade/${V}.0/src
	for script in demo idoc mdltest mkdoc tdoc test2xl vmdltest; do \
		chmod +x ${PREFIX}/share/opencascade/${V}.0/src/DrawResources/$$script; \
	done

.include <bsd.port.mk>
