# 6Harmonics Inc
# maintainer: Qige Zhao
# 2017.03.17 - 2017.04.21

include $(TOPDIR)/rules.mk

PKG_NAME:=grid-base
PKG_VERSION:=1.1
PKG_RELEASE:=5

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE)
PKG_SOURCE_URL:=https://github.com/zhaoqige/6w-grid-base.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=697fb6ee5c98c13ce5990aef8b844f3ef001a08b
PKG_MAINTAINER:=Qige Zhao <qige@6harmonics.com>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE)


include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=GRID base components
  MAINTAINER:=Qige Zhao <qigezhao@gmail.com>
  DEPENDS:=+lua +liblua +libuci-lua +libiwinfo-lua
endef

define Package/$(PKG_NAME)/description
  GRID base components.
  Including basic modules, kpi data collectors.
  As HAL: Hardware Indenpendent.
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_DIR) $(1)/usr/sbin

	$(CP) \
		$(PKG_BUILD_DIR)/lib/* \
		$(1)/usr/lib/lua/
	$(INSTALL_BIN) \
		$(PKG_BUILD_DIR)/bin/* \
		$(1)/usr/sbin/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
