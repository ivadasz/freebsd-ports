# Created by: David O'Brien <obrien@NUXI.com>
# $FreeBSD$

PORTNAME=	ia64sim
PORTVERSION=	0.5
PORTREVISION=	1
CATEGORIES=	emulators
MASTER_SITES=	http://www.boo.net/~jasonp/
DISTNAME=	${PORTNAME}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	IA64 simulator (Intel(R) Architecture 64)

USES=		gmake zip
MAKEFILE=	makefile.unx
MAKE_ARGS=	CC="${CC}"

WRKSRC=		${WRKDIR}/home/chuck/ia64simcc

PLIST_FILES=	bin/ia64sim
PORTDOCS=	ia64user.txt readme

OPTIONS_DEFINE=	DOCS

pre-build:
	${RM} -f ${WRKSRC}/obj/*.o ${WRKSRC}/ia64sim

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/ia64sim ${STAGEDIR}${PREFIX}/bin
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/doc/ia64user.txt ${WRKSRC}/readme \
		${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
