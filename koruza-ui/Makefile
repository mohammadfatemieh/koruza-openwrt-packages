include $(TOPDIR)/rules.mk

PKG_NAME:=koruza-ui
PKG_VERSION:=2016-10-04
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/IRNAS/koruza-ui.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE_VERSION:=bba100795905a045d998827300593b642df6865f
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_MAINTAINER:=Jernej Kos <jernej@kos.mx>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/koruza-ui
  SECTION:=utils
  CATEGORY:=Base system
  TITLE:=KORUZA UI
  DEPENDS:=+koruza-driver +sfp-driver +rpcd +rpcd-mod-iwinfo +uhttpd +uhttpd-mod-ubus +mjpg-streamer +kmod-video-core +kmod-video-uvc
endef

define Package/koruza-ui/description
  KORUZA UI
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/koruza-ui/install
	$(INSTALL_DIR) $(1)/www/koruza
	sed -i 's/<base href="\/">/<base href="\/koruza\/">/' $(PKG_BUILD_DIR)/dist/index.html
	cp -a $(PKG_BUILD_DIR)/dist/* $(1)/www/koruza/
	cp $(PKG_BUILD_DIR)/src/favicon.ico $(1)/www/koruza/
endef

$(eval $(call BuildPackage,koruza-ui))
