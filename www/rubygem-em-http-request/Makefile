# Created by: Scott Sanders <scott@jssjr.com>
# $FreeBSD$

PORTNAME=	em-http-request
PORTVERSION=	1.1.2
CATEGORIES=	www rubygems
MASTER_SITES=	RG

MAINTAINER=	ruby@FreeBSD.org
COMMENT=	EventMachine based, async HTTP Request client

LICENSE=	MIT

RUN_DEPENDS=	rubygem-addressable>=2.3.4:${PORTSDIR}/www/rubygem-addressable \
		rubygem-cookiejar>=0:${PORTSDIR}/www/rubygem-cookiejar \
		rubygem-em-socksify>=0:${PORTSDIR}/www/rubygem-em-socksify \
		rubygem-eventmachine>=1.0.3:${PORTSDIR}/devel/rubygem-eventmachine \
		rubygem-http_parser.rb>=0.6.0:${PORTSDIR}/net/rubygem-http_parser.rb

NO_ARCH=	yes

USE_RUBY=	yes
USE_RUBYGEMS=	yes
RUBYGEM_AUTOPLIST=	yes

.include <bsd.port.mk>
