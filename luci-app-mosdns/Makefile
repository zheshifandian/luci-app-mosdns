include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-mosdns
PKG_VERSION:=1.7.11
PKG_RELEASE:=1

LUCI_TITLE:=LuCI Support for mosdns
LUCI_PKGARCH:=all
LUCI_DEPENDS:=+mosdns +uclient-fetch +v2ray-geoip +v2ray-geosite +geo2txt +ucode

PKG_MAINTAINER:=sbwml <admin@cooluc.com>

define Package/$(PKG_NAME)/conffiles
/etc/config/mosdns
/etc/mosdns/
endef

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
