# Created by: Sergey Skvortsov <skv@protey.ru>
# $FreeBSD$

PORTNAME=	Thrift
PORTVERSION=	${THRIFT_PORTVERSION}	# need to keep this in sync with ../thrift see ../thrift/bsd.thrift.mk
PORTREVISION=	1
PORTEPOCH=	1
CATEGORIES=	devel perl5
PKGNAMEPREFIX=	p5-
DISTFILES=

MAINTAINER=	komarov@valerka.net
COMMENT=	Perl interface to Thrift

BUILD_DEPENDS=	p5-Bit-Vector>=0:${PORTSDIR}/math/p5-Bit-Vector
RUN_DEPENDS=	p5-Bit-Vector>=0:${PORTSDIR}/math/p5-Bit-Vector
FETCH_DEPENDS+=	${NONEXISTENT}:${PORTSDIR}/devel/thrift:extract

USES=		perl5
USE_PERL5=	configure

post-extract:
	@${LN} -sfh \
	`cd ${PORTSDIR}/devel/thrift && ${MAKE} -V WRKSRC`/lib/perl ${WRKSRC}

.include "../thrift/bsd.thrift.mk"
.include <bsd.port.mk>
