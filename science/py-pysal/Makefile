# Created by: Sunpoet Po-Chuan Hsieh <sunpoet@FreeBSD.org>
# $FreeBSD$

PORTNAME=	pysal
PORTVERSION=	1.10.0
CATEGORIES=	science python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	PySAL-${PORTVERSION}

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Cross-platform library of spatial analysis functions

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}numpy>=1.3:${PORTSDIR}/math/py-numpy \
		${PYTHON_PKGNAMEPREFIX}scipy>=0.7:${PORTSDIR}/science/py-scipy
RUN_DEPENDS:=	${BUILD_DEPENDS}
TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}nose>=0:${PORTSDIR}/devel/py-nose

NO_ARCH=	yes
USE_PYTHON=	autoplist distutils
USES=		python:2

.include <bsd.port.mk>
