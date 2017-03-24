# 6Harmonics Inc
# maintainer: Qige Zhao
# 2017.03.15

include $(TOPDIR)/rules.mk

APP_NAME:=app-demo
PKG_NAME:=app-sample
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE)
PKG_SOURCE_URL:=https://github.com/zhaoqige/6w-app-sample.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=320d3f2d81c4400f145a6b9afd6c5e8989b427ca
PKG_MAINTAINER:=Qige Zhao <qige@6harmonics.com>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)_$(PKG_VERSION)-$(PKG_RELEASE)


include $(INCLUDE_DIR)/package.mk
#include $(INCLUDE_DIR)/cmake.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Application sample of package
  MAINTAINER:=Qige Zhao <qigezhao@gmail.com>
#  DEPENDS:=+libiwinfo
endef

define Package/$(PKG_NAME)/description
  Application sample when start a new package.
  Including Makefile, base structure, description.
  And a startup main() function.
endef

# DO NOT add empty "define Package/*", "define Build/*" here
# OR will interrupt the unpack .tar.gz/.tar.bz2 file to $(BUILD_DIR)

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DIR) $(1)/usr/sbin

	$(INSTALL_CONF) $(PKG_BUILD_DIR)/$(PKG_NAME).conf $(1)/etc/config/$(APP_NAME)
	$(INSTALL_BIN) 	$(PKG_BUILD_DIR)/$(PKG_NAME).init $(1)/etc/init.d/$(APP_NAME)
	$(INSTALL_BIN) 	$(PKG_BUILD_DIR)/$(APP_NAME) $(1)/usr/sbin/$(APP_NAME)
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
