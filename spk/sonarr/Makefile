SPK_NAME = nzbdrone
SPK_VERS = $(shell date +%Y%m%d)
SPK_REV = 19
SPK_ICON = src/sonarr.png

# Mono not supported on ppc platforms. C.f. cross/mono/Makefile and references therein for details.
UNSUPPORTED_ARCHS = $(PPC_ARCHS)

DEPENDS = cross/curl cross/mediainfo cross/sqlite cross/sonarr

SPK_DEPENDS = "mono>3.6"

MAINTAINER = SynoCommunity
DESCRIPTION = Sonarr is a PVR for newsgroup and torrent users. It can monitor multiple RSS feeds for new episodes of your favourite shows and will grab, sorts and rename them. It can also be configured to automatically upgrade the quality of files already downloaded if a better quality format becomes available.
DESCRIPTION_FRE = Sonarr est un PVR pour les utilisateurs de groupes de discussion et torrents. Il peut surveiller plusieurs flux RSS pour les nouveaux épisodes de vos séries préférées et saisira, sortes et les renomme. Il peut également être configuré pour mettre à jour automatiquement la qualité des fichiers déjà téléchargés si un meilleur format de qualité devient disponible.
DESCRIPTION_SPN = Sonarr es un PVR para los usuarios de grupos de noticias y torrents. Se puede controlar múltiples canales RSS para nuevos episodios de sus programas favoritos y se agarra, tipo y les cambia el nombre. También puede ser configurado para actualizar automáticamente la calidad de los archivos ya descargados si un formato de mejor calidad disponible.
DISPLAY_NAME = Sonarr
STARTABLE = yes
CHANGELOG = "Update Sonarr to v3.0.5.1144"

HOMEPAGE = https://sonarr.tv
LICENSE  = GPLv3

SERVICE_USER = auto
SERVICE_SETUP = src/service-setup.sh
SERVICE_PORT = 8989
SERVICE_PORT_TITLE = $(DISPLAY_NAME)

# Admin link for in DSM UI
ADMIN_PORT = $(SERVICE_PORT)

WIZARDS_DIR = src/wizard/

POST_STRIP_TARGET = sonarr_extra_install

include ../../mk/spksrc.spk.mk

.PHONY: sonarr_extra_install
sonarr_extra_install:
	install -m 755 -d $(STAGING_DIR)/app
