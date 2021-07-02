# $NetBSD$

DISTNAME=	starship-0.55.0
PKGREVISION=	1
CATEGORIES=	shells
GITHUB_TAG=	v${PKGVERSION_NOREV}
MASTER_SITES=	${MASTER_SITE_GITHUB:=starship/}

MAINTAINER=	mj@mjturner.net
HOMEPAGE=	https://github.com/starship/starship/
COMMENT=	Fast, customizable cross-shell prompt
LICENSE=	isc

# The libc and rust-battery crates currently have limited platform support
ONLY_FOR_PLATFORM=	Darwin-*-* DragonFly-*-* FreeBSD-*-* Linux-*-* NetBSD-*-*

LIBC_REV=	4fcfa55fbbd40e8471865203fcdb52cfac1ec2a7
DISTFILES=	${DEFAULT_DISTFILES}
DISTFILES+=	libc-${LIBC_REV}.tar.gz
SITES.libc-${LIBC_REV}.tar.gz+=	-${MASTER_SITE_GITHUB:=rust-lang/}libc/archive/${LIBC_REV}.tar.gz

USE_LANGUAGES=			c
RUST_REQ?=			1.51.0

CARGO_NO_DEFAULT_FEATURES=	YES
CARGO_FEATURES+=		http
.include "../../mk/bsd.prefs.mk"
.if ${OPSYS} == "Darwin" || ${OPSYS} == "DragonFly" || ${OPSYS} == "FreeBSD" || ${OPSYS} == "Linux"
CARGO_FEATURES+=	battery
.endif

.include "cargo-depends.mk"

INSTALLATION_DIRS=	bin

post-extract:
	mv ${WRKDIR}/libc-* ${WRKSRC}

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/target/release/starship ${DESTDIR}${PREFIX}/bin

.include "../../lang/rust/cargo.mk"
.include "../../mk/bsd.pkg.mk"
