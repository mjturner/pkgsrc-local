# $NetBSD: Makefile,v 1.22 2020/01/26 17:31:54 rillig Exp $

DISTNAME=	s3cmd-2.1.0
PKGNAME=	${PYPKGPREFIX}-${DISTNAME}
PKGREVISION=	1
CATEGORIES=	python net
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=s3tools/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://s3tools.org/s3cmd
COMMENT=	Command-line interface to Amazon's Simple Storage Service (S3)
LICENSE=	gnu-gpl-v2

PYDISTUTILSPKG=		yes
MAKE_ENV+=		S3CMD_INSTPATH_MAN=${PKGMANDIR}

PYTHON_SELF_CONFLICT=		yes
PYTHON_VERSIONS_ACCEPTED=	27 36 37 38

.include "../../lang/python/pyversion.mk"

DEPENDS+=	${PYPKGPREFIX}-expat-[0-9]*:../../textproc/py-expat

.include "../../lang/python/egg.mk"
.include "../../lang/python/application.mk"
.include "../../mk/bsd.pkg.mk"
