# Created by: Marcin Cieslak <saper@SYSTEM.PL>
# $FreeBSD$

PORTNAME=	tinypy
PORTVERSION=	1.1
PORTREVISION=	1
CATEGORIES=	lang python
MASTER_SITES=	GOOGLE_CODE

MAINTAINER=	saper@saper.info
COMMENT=	Minimalist implementation of python in 64k of code

LICENSE=	MIT PSFL
LICENSE_COMB=	multi
LICENSE_FILE=	LICENSE.txt

USES=		python:build
USE_PYTHON=	distutils noegginfo

PYDISTUTILS_BUILD_TARGET=	linux

PLIST_FILES=	bin/tinypy

OPTIONS_DEFINE=	PYGAME EXAMPLES
PYGAME_DESC=	PyGame support (requires SDL)

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MPYGAME}
PYDISTUTILS_BUILD_TARGET+=	pygame
USE_SDL=	sdl
PORTEXAMPLES=	*
.endif

.include <bsd.port.pre.mk>

post-patch:
	@${REINPLACE_CMD} -e 's|-O.||; s|gcc $$WFLAGS|${CC} ${CFLAGS} -std=c89 -Wall|' \
		-e 's|python |${PYTHON_CMD} |g' \
		${WRKSRC}/setup.py

do-configure:
	@${DO_NADA}

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/build/tinypy ${STAGEDIR}${PREFIX}/bin
.if ${PORT_OPTIONS:MEXAMPLES} && ${PORT_OPTIONS:MPYGAME}
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	${INSTALL_DATA} ${WRKSRC}/examples/julia.py ${STAGEDIR}${EXAMPLESDIR}
.endif

.include <bsd.port.post.mk>
