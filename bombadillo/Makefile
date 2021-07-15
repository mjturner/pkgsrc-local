# $NetBSD$

DISTNAME=	bombadillo-2.3.3
CATEGORIES=	net
MASTER_SITES=	-https://tildegit.org/sloum/bombadillo/archive/${PKGVERSION_NOREV}.tar.gz

MAINTAINER=	mj@mjturner.net
HOMEPAGE=	https://tildegit.org/sloum/bombadillo/archive/
COMMENT=	Non-web browser for the terminal
LICENSE=	gnu-gpl-v3

WRKSRC=		${WRKDIR}/${DISTNAME:S/-${PKGVERSION_NOREV}//}

INSTALLATION_DIRS=	bin share/applications ${PKGMANDIR}/man1

do-install:
	${INSTALL_PROGRAM} ${WRKDIR}/.gopath/bin/bombadillo ${DESTDIR}${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/bombadillo.1 ${DESTDIR}${PREFIX}/${PKGMANDIR}/man1
	${INSTALL_DATA} ${WRKSRC}/bombadillo.desktop ${DESTDIR}${PREFIX}/share/applications

.include "../../lang/go/go-module.mk"
.include "../../mk/bsd.pkg.mk"
