# $OpenBSD$

COMMENT =		Device Firmware Update based USB programmer for Atmel chips

V =			0.5.4
DISTNAME =		dfu-programmer-${V}

# for any port that creates shared libraries.
# both libtool and cmake handle this automatically.
# for libtool-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =		???

CATEGORIES =		devel

HOMEPAGE =		http://dfu-programmer.sourceforge.net/

# GPL
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

# "make port-lib-depends-check" can help
WANTLIB =		c usb

LIB_DEPENDS =		devel/libusb

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=dfu-programmer/}

CONFIGURE_STYLE =	gnu
CONFIGURE_ENV =		CPPFLAGS="${CPPFLAGS} -I${LOCALBASE}/include" \
			CFLAGS="${CFLAGS} -I${LOCALBASE}/include" \
			LDFLAGS="${CFLAGS} -L${LOCALBASE}/lib"

.include <bsd.port.mk>
