# Created by: vanilla@
# $FreeBSD$

PORTNAME=	google-apputils
PORTVERSION=	0.4.2
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	vanilla@FreeBSD.org
COMMENT=	Google Application Utilities for Python

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}gflags>2:${PORTSDIR}/devel/py-gflags \
		${PYTHON_PKGNAMEPREFIX}pytz>0:${PORTSDIR}/devel/py-pytz \
		${PYTHON_PKGNAMEPREFIX}dateutil>2:${PORTSDIR}/devel/py-dateutil

USES=		python:2
USE_PYTHON=	distutils autoplist

post-extract:
	@${CHMOD} -R a+rX ${WRKSRC}

.include <bsd.port.mk>
