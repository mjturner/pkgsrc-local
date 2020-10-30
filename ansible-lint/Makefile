# $NetBSD$

DISTNAME=	ansible-lint-4.3.5
PKGNAME=	${PYPKGPREFIX}-${DISTNAME}
CATEGORIES=	sysutils python
MASTER_SITES=	${MASTER_SITE_PYPI:=p/ansible-lint/}

PYTHON_VERSIONS_INCOMPATIBLE=	27

MAINTAINER=	mj@mjturner.net
HOMEPAGE=	https://github.com/ansible/ansible-lint/
COMMENT=	Command-line tool for linting Ansible playbooks
LICENSE=	mit

USE_TOOLS+=	pax

EGDIR=		${PREFIX}/share/examples/ansible-lint

DEPENDS+=	ansible>=2.8:../../sysutils/ansible
DEPENDS+=	${PYPKGPREFIX}-yaml:../../textproc/py-yaml
DEPENDS+=	${PYPKGPREFIX}-pygments<3.0.0,>=2.6.0:../../textproc/py-pygments
DEPENDS+=	${PYPKGPREFIX}-rich:../../wip/py-rich
DEPENDS+=	${PYPKGPREFIX}-ruamel-yaml>=0.15.37:../../devel/py-ruamel-yaml

INSTALLATION_DIRS=	bin ${EGDIR}

post-install:
	cd ${WRKSRC}/examples && ${PAX} -rw . ${DESTDIR}${EGDIR}

USE_LANGUAGES=	# none

# TODO: Migrate MASTER_SITES to MASTER_SITE_PYPI
.include "../../lang/python/egg.mk"
.include "../../mk/bsd.pkg.mk"
