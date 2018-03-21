include $(TOPDIR)/rules.mk

PKG_NAME:=perl-weather
PKG_VERSION:=0.5.5
PKG_RELEASE:=1
PKG_SOURCE_URL:=http://search.cpan.org/CPAN/authors/id/S/SC/SCHNUECK
PKG_HASH:=0032c79d4181f603d02dbc01dd496726239a48ce3fcd2945e211155aae176d34

PKG_SOURCE:=Weather-Com-$(PKG_VERSION).tar.gz
PKG_CAT:=zcat

PKG_BUILD_DIR:=$(BUILD_DIR)/perl/Weather-Com-$(PKG_VERSION)
# PKG_INSTALL_DIR:=$(PKG_BUILD_DIR)/ipkg-install

include $(INCLUDE_DIR)/package.mk
include ../perl/perlmod.mk

define Package/$(PKG_NAME)
SUBMENU:=Perl
SECTION:=lang
CATEGORY:=Languages
TITLE:=A module fetching weather information from weather.com
DEPENDS:=perl
endef

define Build/Configure
        $(call perlmod/Configure,-n,)
endef

define Build/Compile
        $(call perlmod/Compile,,)
endef

define Package/$(PKG_NAME)/install
        $(call perlmod/Install,$(1),Weather auto/Weather)
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
