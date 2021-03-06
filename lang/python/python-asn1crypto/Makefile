#
# Copyright (C) 2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-asn1crypto
PKG_VERSION:=1.2.0
PKG_RELEASE:=1

PKG_SOURCE:=asn1crypto-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.io/packages/source/a/asn1crypto
PKG_HASH:=87620880a477123e01177a1f73d0f327210b43a3cdbd714efcd2fa49a8d7b384

PKG_LICENSE:=MIT
PKG_MAINTAINER:=Alexandru Ardelean <ardeleanalex@gmail.com>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-asn1crypto-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-asn1crypto/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  URL:=https://github.com/wbond/asn1crypto
endef

define Package/python-asn1crypto
$(call Package/python-asn1crypto/Default)
  TITLE:=python-asn1crypto
  DEPENDS:=+PACKAGE_python-asn1crypto:python-light
  VARIANT:=python
endef

define Package/python3-asn1crypto
$(call Package/python-asn1crypto/Default)
  TITLE:=python3-asn1crypto
  DEPENDS:=+PACKAGE_python3-asn1crypto:python3-light
  VARIANT:=python3
endef

define Package/python-asn1crypto/description
Fast ASN.1 parser and serializer with definitions for
private keys, public keys, certificates, CRL, OCSP,
CMS, PKCS#3, PKCS#7, PKCS#8, PKCS#12, PKCS#5, X.509 and TSP
endef

define Package/python3-asn1crypto/description
$(call Package/python-asn1crypto/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-asn1crypto))
$(eval $(call BuildPackage,python-asn1crypto))
$(eval $(call BuildPackage,python-asn1crypto-src))

$(eval $(call Py3Package,python3-asn1crypto))
$(eval $(call BuildPackage,python3-asn1crypto))
$(eval $(call BuildPackage,python3-asn1crypto-src))
