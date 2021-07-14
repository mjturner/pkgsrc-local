# $NetBSD$

DISTNAME=	dua-cli-2.14.2
CATEGORIES=	sysutils
MASTER_SITES=	${MASTER_SITE_GITHUB:=Byron/}
GITHUB_TAG=	v${PKGVERSION_NOREV}

MAINTAINER=	mj@mjturner.net
HOMEPAGE=	https://github.com/Byron/dua-cli/
COMMENT=	Disk usage analyzer
LICENSE=	mit

.include	"cargo-depends.mk"

USE_LANGUAGES=	c

INSTALLATION_DIRS=	bin

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/target/release/dua ${DESTDIR}${PREFIX}/bin

.include "../../lang/rust/cargo.mk"
.include "../../mk/bsd.pkg.mk"
