# $NetBSD$

DISTNAME=		gitea-src-1.14.5
PKGNAME=		${DISTNAME:S/src-//}
CATEGORIES=		devel
MASTER_SITES=		${MASTER_SITE_GITHUB:=go-gitea/}

MAINTAINER=		mj@mjturner.net
HOMEPAGE=		https://github.com/go-gitea/gitea/
COMMENT=		Self-hosted Git service
LICENSE=		mit

WRKSRC=			${WRKDIR}/${PKGNAME_NOREV}
USE_TOOLS+=		gmake

MAKE_ENV+=		TAGS=bindata
# sqlite sqlite_unlock_notify"
BUILD_TARGET=		build
INSTALLATION_DIRS=	bin

do-extract:
	${MKDIR} ${WRKSRC}
	${RUN} cd ${WRKSRC} && ${TAR} xf ${DISTDIR}/${DISTNAME}${EXTRACT_SUFX}

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/gitea ${DESTDIR}${PREFIX}/bin

#.include "../../lang/go/go-module.mk"
.include "../../mk/bsd.pkg.mk"
