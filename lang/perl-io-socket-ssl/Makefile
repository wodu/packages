#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=perl-io-socket-ssl
PKG_VERSION:=2.056
PKG_RELEASE:=1

PKG_SOURCE_URL:=http://search.cpan.org/CPAN/authors/id/S/SU/SULLR/
PKG_SOURCE:=IO-Socket-SSL-$(PKG_VERSION).tar.gz
PKG_HASH:=91451ecc28b243a78b438f0a42db24c4b60a86f088879b38e40bdbd697818259

PKG_LICENSE:=GPL-1.0+ Artistic-1.0-Perl
PKG_MAINTAINER:=Marcel Denia <naoir@gmx.net>

PKG_BUILD_DIR:=$(BUILD_DIR)/perl/IO-Socket-SSL-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include ../perl/perlmod.mk

define Package/perl-io-socket-ssl
  SUBMENU:=Perl
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=SSL sockets with IO::Socket interface
  URL:=httpw://search.cpan.org/~sullr/IO-Socket-SSL-2.056/lib/IO/Socket/SSL.pod
  DEPENDS:=perl +perlbase-essential +perl-net-ssleay
endef

define Build/Configure
        $(call perlmod/Configure,,)
endef

define Build/Compile
        $(call perlmod/Compile,,)
endef

define Package/perl-io-socket-ssl/install
        $(call perlmod/Install,$(1),IO auto/IO)
endef


$(eval $(call BuildPackage,perl-io-socket-ssl))
