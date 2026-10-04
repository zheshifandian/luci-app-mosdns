# SPDX-License-Identifier: GPL-3.0-only
#
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=mosdns
PKG_VERSION:=5.3.5
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/maoxikun/mosdns.git
PKG_SOURCE_DATE:=2026-09-29
PKG_MIRROR_HASH:=ed1fb7c10024cca3aa7962fb375726f8ba302d8567d58429dc96e995ed9941b6
PKG_SOURCE_VERSION:=047702c2e7b4f6ddd32c2eb2281ccca54b855cf0

PKG_LICENSE:=GPL-3.0
PKG_LICENSE_FILE:=LICENSE
PKG_MAINTAINER:=Tianling Shen <cnsztl@immortalwrt.org>

PKG_BUILD_DEPENDS:=golang/host
PKG_BUILD_PARALLEL:=1
PKG_BUILD_FLAGS:=no-mips16

GO_PKG:=github.com/IrineSistiana/mosdns
GO_PKG_LDFLAGS_X:=main.version=v$(PKG_VERSION)-r$(PKG_RELEASE)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/golang/golang-package.mk

define Package/mosdns
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=IP Addresses and Names
  TITLE:=A plug-in DNS forwarder/splitter
  URL:=https://github.com/IrineSistiana/mosdns
  DEPENDS:=$(GO_ARCH_DEPENDS) +ca-bundle
endef

define Package/mosdns/description
MosDNS is a flexible, plugin-driven DNS resolver/forwarder written in Go.
Supports DNS split routing, DoH/DoT/QUIC upstream, custom rule filtering,
cache acceleration and customized DNS policy for home routers.
endef

define Package/mosdns/install
	$(call GoPackage/Package/Install/Bin,$(1))
endef

$(eval $(call GoBinPackage,mosdns))
$(eval $(call BuildPackage,mosdns))
