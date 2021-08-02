# $NetBSD: Makefile,v 1.2 2020/11/05 08:31:29 maya Exp $

DISTNAME=	git-delta-0.8.3
CATEGORIES=	textproc
EXTRACT_SUFX=	.crate

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://github.com/dandavison/delta/
COMMENT=	Viewer for git and diff output
LICENSE=	mit

WRKSRC=		${WRKDIR}/${PKGNAME_NOREV}
USE_LANGUAGES=	c

.include "cargo-depends.mk"

INSTALLATION_DIRS=	bin

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/target/release/delta ${DESTDIR}${PREFIX}/bin

.include "../../lang/rust/cargo.mk"
.include "../../mk/bsd.pkg.mk"
