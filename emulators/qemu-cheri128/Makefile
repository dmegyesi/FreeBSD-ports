# Created by: Brooks Davis
# $FreeBSD$

PKGNAMESUFFIX=	-cheri128

COMMENT=	QEMU emulator with CHERI CPU support (128-bit)

RUN_DEPENDS=	qemu-system-cheri:emulators/qemu-cheri

MASTERDIR=	${.CURDIR}/../qemu-cheri

EXTRA_CFLAGS=	-DCHERI_MAGIC128
PLIST=		/dev/null
PLIST_FILES=	bin/qemu-system-cheri128

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/cheri-softmmu/qemu-system-cheri \
	    ${STAGEDIR}${PREFIX}/bin/qemu-system-cheri128

.include <${MASTERDIR}/Makefile>
