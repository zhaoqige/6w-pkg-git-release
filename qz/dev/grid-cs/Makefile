# 6Harmonics Inc
# maintainer: Qige Zhao
# 2017.04.21

include $(TOPDIR)/rules.mk

APP_NAME:=grid-cs
PKG_NAME:=grid-cs
PKG_VERSION:=1.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE)
PKG_SOURCE_URL:=https://github.com/zhaoqige/6w-grid-cs.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=1477e3927de64732293a0a07899ec88fe4844e83
PKG_MAINTAINER:=Qige Zhao <qige@6harmonics.com>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE)


include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Channel Scanner based on GRID
  MAINTAINER:=Qige Zhao <qigezhao@gmail.com>
  DEPENDS:=+grid-base
endef

define Package/$(PKG_NAME)/description
  Channel Scanner based on GRID.
  Will restore region/channel/rxagc/rxgain when done.
  Can be configured by file.
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_DIR) $(1)/etc/init.d

	$(CP) \
		$(PKG_BUILD_DIR)/lib/* \
		$(1)/usr/lib/lua/
	$(INSTALL_BIN) \
		$(PKG_BUILD_DIR)/bin/* \
		$(1)/usr/sbin/
	$(INSTALL_BIN) \
		$(PKG_BUILD_DIR)/$(PKG_NAME).init \
		$(1)/etc/init.d/$(APP_NAME)
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
