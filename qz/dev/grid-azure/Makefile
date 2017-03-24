# 6Harmonics Inc
# maintainer: Qige Zhao
# 2017.03.17

include $(TOPDIR)/rules.mk

APP_NAME:=grid-azure
PKG_NAME:=grid-azure
PKG_VERSION:=1.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE)
PKG_SOURCE_URL:=https://github.com/zhaoqige/6w-grid-azure.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=01750aa199eb563e50b7052807be655fbec8319d
PKG_MAINTAINER:=Qige Zhao <qige@6harmonics.com>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE)


include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Microsoft Azure Agent based on GRID Base
  DEPENDS:=+grid-base +luasocket
  MAINTAINER:=Qige Zhao <qigezhao@gmail.com>
endef

define Package/$(PKG_NAME)/description
	Microsoft Azure Agent based on GRID Base.
	Support Microsoft Azure IoT Hub.
	Protocol: MQTT.
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_DIR) $(1)/etc/init.d

	$(CP) \
		$(PKG_BUILD_DIR)/lib/* \
		$(1)/usr/lib/lua/

	$(INSTALL_CONF) \
		$(PKG_BUILD_DIR)/$(PKG_NAME).conf \
		$(1)/usr/lib/lua/az/$(APP_NAME).conf
	$(INSTALL_CONF) \
		$(PKG_BUILD_DIR)/$(PKG_NAME).conf \
		$(1)/etc/config/$(APP_NAME)

	$(INSTALL_BIN) \
		$(PKG_BUILD_DIR)/bin/$(PKG_NAME) \
		$(1)/usr/sbin/$(APP_NAME)
	$(INSTALL_BIN) \
		$(PKG_BUILD_DIR)/$(PKG_NAME).init \
		$(1)/etc/init.d/$(APP_NAME)
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
