# $FreeBSD: head/multimedia/olive/Makefile 523517 2020-01-19 09:03:14Z yuri $

PORTNAME=	olive-devel
DISTVERSION=	g20200605
CATEGORIES=	multimedia
PKGNAMESUFFIX=	-video-editor

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	NLE (nonlinear) video editor

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	frei0r>0:graphics/frei0r
LIB_DEPENDS=	libavcodec.so:multimedia/ffmpeg \
		libOpenColorIO.so:graphics/opencolorio \
		libOpenImageIO.so:graphics/openimageio \
		libIlmImf.so:graphics/openexr
RUN_DEPENDS=	frei0r>0:graphics/frei0r

USES=		dos2unix qmake compiler:c++11-lang desktop-file-utils gl pkgconfig qt:5 shared-mime-info cmake
USE_GITHUB=	yes
GH_ACCOUNT=	olive-editor
GH_PROJECT=	olive
GH_TAGNAME= 031c07f
USE_QT=		core gui multimedia network opengl svg widgets buildtools_build linguisttools_build concurrent
USE_GL=		gl

CMAKE_ARGS=	-D GIT_HASH:STRING=${GH_TAGNAME} \
	-D OIIO_BASE_DIR:PATH=${PREFIX}

DATADIR=	${PREFIX}/share/olive-editor
MAKE_ENV=	DESTDIR="${STAGEDIR}"

.include <bsd.port.mk>
