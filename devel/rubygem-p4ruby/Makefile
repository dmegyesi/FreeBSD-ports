#	$FreeBSD$

PORTNAME=	p4ruby
PORTVERSION=	2015.2.1313860
CATEGORIES=	devel rubygems
MASTER_SITES=	RG

MAINTAINER=	brd@FreeBSD.org
COMMENT=	Ruby bindings for the Perforce API

LICENSE=	BSD2CLAUSE

BUILD_DEPENDS+=	${LOCALBASE}/lib/perforce/libclient.a:devel/p4api
RUN_DEPENDS:=	${BUILD_DEPENDS}

USE_RUBY=	yes
USE_RUBYGEMS=	yes
RUBYGEM_AUTOPLIST=	yes

CONFIGURE_ARGS=	--with-p4api-dir=${LOCALBASE} --with-p4api-lib=${LOCALBASE}/lib/perforce

.include	<bsd.port.mk>
