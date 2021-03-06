# Created by: Alexander Vereeken <Alexander88207@protonmail.com>
# $FreeBSD$

PORTNAME=	homura
PORTVERSION=	5.1
CATEGORIES=	games

MAINTAINER=	Alexander88207@protonmail.com
COMMENT=	Windows Games Launcher for FreeBSD

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

ONLY_FOR_ARCHS=	amd64 i386
ONLY_FOR_ARCHS_REASON=	Wine only runs on x86 architecture

RUN_DEPENDS=	zenity:x11/zenity \
		xdg-open:devel/xdg-utils \
		bash:shells/bash \
		7z:archivers/p7zip \
		webfonts>=0:x11-fonts/webfonts \
		winetricks:emulators/winetricks \
		vulkaninfo:devel/vulkan-tools \
		glxinfo:graphics/mesa-demos

USE_GITLAB=	yes
GL_ACCOUNT=	Alexander88207
GL_PROJECT=	Homura
GL_COMMIT=	d6270c8cc207e65073b743949274cacb84caf014

NO_BUILD=	yes

PLIST_FILES=	bin/Homura

.include <bsd.port.pre.mk>

.if ${ARCH} == "i386"
RUN_DEPENDS+=	wine:emulators/wine
.else
RUN_DEPENDS+=	wine:emulators/i386-wine
.endif

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/Homura ${STAGEDIR}${PREFIX}/bin

.include <bsd.port.post.mk>
