SPK_NAME = python3
SPK_VERS = 3.7.12
SPK_SHORT_VERS = $(word 1,$(subst ., ,$(SPK_VERS))).$(word 2,$(subst ., ,$(SPK_VERS)))
SPK_REV = 21
SPK_ICON = src/python3.png

DEPENDS  = cross/busybox cross/$(SPK_NAME)
DEPENDS += cross/setuptools cross/pip cross/wheel
DEPENDS += cross/cffi cross/bcrypt cross/sqlite
# Cross-compiled wheels
DEPENDS += cross/lxml cross/pycrypto cross/pycurl cross/pyyaml
DEPENDS += cross/msgpack-python cross/ruamel.yaml cross/immutables
DEPENDS += cross/cryptography

WHEELS = src/requirements-crossenv.txt src/requirements-pure.txt

MAINTAINER = chickenandpork
DESCRIPTION = Python Programming Language.
DESCRIPTION_FRE = Langage de programmation Python.
DESCRIPTION_SPN = Lenguaje de programación Python.

STARTABLE = no
DISPLAY_NAME = Python3
CHANGELOG = "1. Update to Python 3.7.12.<br/>2. Update OpenSSL to v1.1.1l<br/>3. Update all requirements.txt"

HOMEPAGE = https://www.python.org
LICENSE  = PSF

SERVICE_SETUP = src/service-setup.sh

PYTHON_LIB_DIR = lib/python$(SPK_SHORT_VERS)

POST_STRIP_TARGET = python3_extra_install

BUSYBOX_CONFIG = usrmng nice daemon patch
ENV += BUSYBOX_CONFIG="$(BUSYBOX_CONFIG)"

include ../../mk/spksrc.spk.mk

.PHONY: python3_extra_install
python3_extra_install:
	rm -f $(STAGING_DIR)/$(PYTHON_LIB_DIR)/config/libpython*.a
	rm -rf $(STAGING_DIR)/$(PYTHON_LIB_DIR)/test/
	find $(STAGING_DIR)/$(PYTHON_LIB_DIR) -type f -regex '.*\.py[co]' | xargs rm -f
