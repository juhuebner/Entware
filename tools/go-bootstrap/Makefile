#
# Copyright (C) 2016-2019 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=go-bootstrap
PKG_VERSION:=1.4.3
PKG_VERSION:=1.19
OS=$(shell uname | tr 'A-Z' 'a-z')
bintype:=$(shell uname -m | sed \
        -e 's/i[3-9]86/386/' \
        -e 's/x86_64/amd64/' \
)
ifeq ($(bintype),armv7l)
  bintype:=armv6l
endif

PKG_SOURCE:=go$(PKG_VERSION).$(OS)-$(bintype).tar.gz
PKG_HASH:=25197c7d70c6bf2b34d7d7c29a2ff92ba1c393f0fb395218f1147aac2948fb93
PKG_SOURCE_URL:=https://go.dev/dl/
HOST_BUILD_DIR:=$(STAGING_DIR_HOST)/go$(PKG_VERSION)
HOST_UNPACK:=gzip -dc $(DL_DIR)/$(PKG_SOURCE) | tar -C $(HOST_BUILD_DIR) --strip-components=1 -xf -

include $(INCLUDE_DIR)/host-build.mk

#build go for all architetures - in case gccgo does not work

define Host/Compile
endef

define Host/Install
endef

define Host/Clean
	rm -rf $(STAGING_DIR_HOST)/go$(PKG_VERSION)
endef

$(eval $(call HostBuild))
