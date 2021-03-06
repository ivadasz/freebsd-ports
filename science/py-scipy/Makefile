# Created by: ijliao
# $FreeBSD$

PORTNAME=	scipy
PORTVERSION=	0.16.0
CATEGORIES=	science python
MASTER_SITES=	http://docs.scipy.org/doc/${DISTNAME}/:doc \
		SF:source
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTFILES=	${DISTNAME}${EXTRACT_SUFX}:source \
		scipy-ref-${PORTVERSION}.pdf:doc
EXTRACT_ONLY=	${DISTNAME}${EXTRACT_SUFX}

MAINTAINER=	python@FreeBSD.org
COMMENT=	Scientific tools for Python

LICENSE=	BSD3CLAUSE

BUILD_DEPENDS=	${PYNUMPY}
RUN_DEPENDS=	${PYNUMPY} \
		swig:${PORTSDIR}/devel/swig13

USES=		fortran python
USE_PYTHON=	autoplist concurrent distutils
LDFLAGS+=	-shared
PYDISTUTILS_BUILDARGS=	--fcompiler=gnu95
PYDISTUTILS_CONFIGUREARGS=	--fcompiler=gnu95

OPTIONS_DEFINE=	DOCS

PORTDOCS=	scipy-ref-${PORTVERSION}.pdf

post-extract:
	@${CP} ${DISTDIR}/scipy-ref-${PORTVERSION}.pdf ${WRKDIR}

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKDIR}/scipy-ref-${PORTVERSION}.pdf ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
