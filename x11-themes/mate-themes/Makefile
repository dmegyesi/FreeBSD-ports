# Created by: Joe Marcus Clarke <marcus@FreeBSD.org>
# $FreeBSD$

PORTNAME=	mate-themes
PORTVERSION=	1.12.2
PORTREVISION=	1
CATEGORIES=	x11-themes mate
MASTER_SITES=	MATE
DIST_SUBDIR=	mate
DISTNAME=	${PORTNAME}-gtk3.18-${PORTVERSION}

MAINTAINER=	gnome@FreeBSD.org
COMMENT=	Collection of themes and icons for MATE

BUILD_DEPENDS=	gtk-engines2>=2.15.0:x11-themes/gtk-engines2 \
		icon-naming-utils>=0.8.7:x11-themes/icon-naming-utils
RUN_DEPENDS=	gtk-engines2>=2.15.0:x11-themes/gtk-engines2 \
		gtk-murrine-engine>=0.98:x11-themes/gtk-murrine-engine

PORTSCOUT=	limitw:1,even

USES=		gettext gmake pathfix pkgconfig tar:xz
USE_MATE=	marco
USE_GNOME=	gdkpixbuf2 gtk20 intlhack
GNU_CONFIGURE=	yes
INSTALLS_ICONS=	yes
CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib

.include <bsd.port.mk>
