# Created by: Thierry Thomas <thierry@pompo.net>
# $FreeBSD$

PORTNAME=	twister-core
PORTVERSION=	0.9.30
DISTVERSIONPREFIX=	v
PORTEPOCH=	1
CATEGORIES=	net-p2p

MAINTAINER=	thierry@FreeBSD.org
COMMENT=	Experimental peer-to-peer microblogging software

LICENSE=	BSD3CLAUSE MIT
LICENSE_COMB=	dual
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libboost_system.so:${PORTSDIR}/devel/boost-libs	\
		libleveldb.so:${PORTSDIR}/databases/leveldb	\
		libicui18n.so:${PORTSDIR}/devel/icu

OPTIONS_DEFINE=	DOCS

USE_GITHUB=	yes
GH_ACCOUNT=	miguelfreitas

USE_BDB=	yes
WANT_BDB_VER=	48
USE_OPENSSL=	yes
USES=		autoreconf:build gmake iconv libtool

GNU_CONFIGURE=	yes
CONFIGURE_WRKSRC=${WRKSRC}/libtorrent
CONFIGURE_ARGS=	--with-libiconv			\
		--with-boost=${LOCALBASE}	\
		--with-boost-system=boost_system
MAKEFILE=	makefile.freebsd
BUILD_WRKSRC=	${WRKSRC}/src
MAKE_ENV=	BOOST_INCLUDE_PATH=${LOCALBASE}/include	\
		BOOST_LIB_PATH=${LOCALBASE}/lib		\
		BDB_INCLUDE_PATH=${BDB_INCLUDE_DIR}	\
		BDB_LIB_PATH=${BDB_LIB_DIR}		\
		ICONV_LIB="${ICONV_LIB}"

PLIST_FILES=	bin/twisterd
PORTDOCS=	README.md

.include <bsd.port.options.mk>

.if (${OPSYS} == FreeBSD && ${OSVERSION} < 1000000)
WITH_OPENSSL_PORT=	yes
.endif

post-patch:
	@${REINPLACE_CMD} 's|%%PORTVERSION%%|${PORTVERSION}|'	\
		${WRKSRC}/share/genbuild.sh

pre-configure:
	(cd ${CONFIGURE_WRKSRC} && ./autotool.sh)

do-install:
	${INSTALL_PROGRAM} ${BUILD_WRKSRC}/twisterd ${STAGEDIR}${PREFIX}/bin

do-install-DOCS-on:
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/README.md ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
