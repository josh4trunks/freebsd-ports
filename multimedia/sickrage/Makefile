# $FreeBSD$

PORTNAME=	sickrage
PORTVERSION=	20170521
CATEGORIES=	multimedia

MAINTAINER=	joshruehlig@gmail.com
COMMENT=	Video File Manager for TV Shows

LICENSE=	GPLv3

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}sqlite3>0:databases/py-sqlite3 \
		${PYTHON_PKGNAMEPREFIX}lxml>0:devel/py-lxml
#		${PYTHON_PKGNAMEPREFIX}imaging>0:graphics/py-pillow

USE_GITHUB=	yes
GH_ACCOUNT=	SickRage
GH_PROJECT=	SickRage
GH_TAGNAME=	v2017.05.21-1

USES=		python:2.7

NO_ARCH=	yes
NO_BUILD=	yes
SUB_LIST=	PYTHON_CMD=${PYTHON_CMD} USERS=${USERS}
USE_RC_SUBR=	sickrage

USERS=		_sabnzbd
GROUPS=		_sabnzbd

OPTIONS_DEFINE=	OPENSSL UNRAR

OPENSSL_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}openssl>0:security/py-openssl
UNRAR_RUN_DEPENDS=	unrar:archivers/unrar

do-install:
	${MKDIR} ${STAGEDIR}${DATADIR}
	(cd ${WRKSRC} && ${COPYTREE_SHARE} . ${STAGEDIR}${DATADIR})

.include <bsd.port.mk>
