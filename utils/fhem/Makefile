include $(TOPDIR)/rules.mk

PKG_NAME:=fhem
PKG_VERSION:=5.8
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://fhem.de/
PKG_HASH:=879133025dbbb803d5a59a0deaef1441ba6bf11d67c9961bc353e2df5501746c

include $(INCLUDE_DIR)/package.mk

define Package/fhem
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Fhem is a GPL'd perl server for house automation.
  MAINTAINER:=Philipp Strobel
  URL:=http://fhem.de/fhem.html
  DEPENDS:=+libgd +zlib +perl +perlbase-autoloader +perlbase-config +perlbase-dynaloader +perlbase-errno +perlbase-essential +perlbase-fcntl +perlbase-io +perlbase-math +perlbase-posix +perlbase-selectsaver +perlbase-socket +perlbase-symbol +perlbase-tie +perlbase-time +perlbase-xsloader +perlbase-file +perlbase-bytes +perlbase-compress +perlbase-list +perlbase-scalar +perlbase-utf8 +perl-device-serialport +kmod-usb-acm +perlbase-version +perlbase-filter +perlbase-text +perlbase-selfloader +perlbase-feature +libusb-compat +perl-weather +usbutils
endef

define Package/fhem/Description 
    Fhem is a GPL'd perl server for house automation. 
    It is used to automate some common tasks in the household like switching lamps / shutters / heating / etc. and to log events like temperature/humidity/power consumption. The program runs as a server, you can control it via web-frontends, telnet, command line program or TCP/IP directly.
    original makefile from: http://samtrac.informatik.hu-berlin.de/seismo-openwrt/
endef 

BINDIR:=/opt/fhem
VARDIR:=/data/log/fhem
ETCDIR:=/etc

define Package/fhem/conffiles
/etc/fhem.cfg
endef

define Package/fhem/install
	$(INSTALL_DIR) $(1)$(BINDIR)
	$(INSTALL_DIR) $(1)$(VARDIR)
	$(INSTALL_DIR) $(1)$(ETCDIR)
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fhem.pl $(1)$(BINDIR)
	$(CP) $(PKG_BUILD_DIR)/configDB.pm $(1)$(BINDIR)
	$(CP) $(PKG_BUILD_DIR)/fhem.cfg $(1)$(ETCDIR)
	$(CP) $(PKG_BUILD_DIR)/FHEM $(1)$(BINDIR)
	$(CP) $(PKG_BUILD_DIR)/contrib $(1)$(BINDIR)
	$(CP) $(PKG_BUILD_DIR)/www $(1)$(BINDIR)
	$(CP) $(PKG_BUILD_DIR)/docs $(1)$(BINDIR)
	$(INSTALL_BIN) ./files/fhem.init $(1)/etc/init.d/fhem
endef

$(eval $(call BuildPackage,fhem))

