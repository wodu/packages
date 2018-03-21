#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=perl-net-ssleay
PKG_VERSION:=1.85
PKG_RELEASE:=1

PKG_SOURCE_URL:=http://search.cpan.org/CPAN/authors/id/M/MI/MIKEM/
PKG_SOURCE:=Net-SSLeay-$(PKG_VERSION).tar.gz
PKG_HASH:=9d8188b9fb1cae3bd791979c20554925d5e94a138d00414f1a6814549927b0c8

PKG_LICENSE:=GPL-1.0+ Artistic-1.0-Perl
PKG_MAINTAINER:=Marcel Denia <naoir@gmx.net>

PKG_BUILD_DIR:=$(BUILD_DIR)/perl/Net-SSLeay-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include ../perl/perlmod.mk

define Package/perl-net-ssleay
  SUBMENU:=Perl
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Perl extension for using OpenSSL  
  URL:=http://search.cpan.org/~mikem/Net-SSLeay-1.85/lib/Net/SSLeay.pod
  DEPENDS:=perl +perlbase-essential +libopenssl +zlib
endef

define Build/Configure
        $(call perlmod/Configure,INC=" " ,)
endef

define Build/Compile
        $(call perlmod/Compile,,)
endef

define Package/perl-net-ssleay/install
        $(call perlmod/Install,$(1),Net auto/Net)
endef


$(eval $(call BuildPackage,perl-net-ssleay))
