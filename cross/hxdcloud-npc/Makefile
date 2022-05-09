PKG_NAME = hxdcloud-npc
PKG_VERS = 1.0.0
PKG_EXT =
PKG_DIST_NAME = linux_amd64_client
PKG_DIST_SITE = https://api.minio.hxdcloud.com/npc
PKG_DIR = $(PKG_NAME)

# DEPENDS = cross/zlib cross/openssl cross/curl cross/libevent
DEPENDS =

HOMEPAGE = https://transmissionbt.com
COMMENT  = A Fast, Easy, and Free BitTorrent Client
LICENSE  = GPLv2/GPLv3

GNU_CONFIGURE = 1
# CONFIGURE_ARGS = HAVE_CXX=yes --disable-nls --enable-daemon --enable-utp
CONFIGURE_ARGS =

ifeq ($(findstring $(ARCH), ppc824x ppc853x),$(ARCH))
ifneq (5,$(firstword $(sort $(TCVERSION) 5)))
# toolchains before version 5 require the old linux quota version
# related issue: https://github.com/transmission/transmission/issues/591
ADDITIONAL_CFLAGS = -D_LINUX_QUOTA_VERSION=1
endif
endif


include ../../mk/spksrc.cross-cc.mk
