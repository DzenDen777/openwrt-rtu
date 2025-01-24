include $(TOPDIR)/rules.mk

PKG_NAME:=sdb
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git@github.com:DzenDen777/student-db.git
PKG_SOURCE_DATE:=2025-01-21
PKG_SOURCE_VERSION:=364cb234
PKG_MIRROR_HASH:=skip

PKG_MAINTAINER:=Deniss Dz <deniss.dzergacs@edu.rtu.lv>

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=RTU
	CATEGORY:=RTU
	DEPENDS:=+libc
	TITLE:=Student database read/write app
endef

define Package/$(PKG_NAME)/description
	CLI application which allows to enter student 
	and read that afterwise.
endef

define Build/Compile
	$(TARGET_CC) $(TARGET_CFLAGS) $(TARGET_LDFLAGS) \
		-o $(PKG_BUILD_DIR)/student-db \
		$(PKG_BUILD_DIR)/main.c \
		$(PKG_BUILD_DIR)/inout.c \
		$(PKG_BUILD_DIR)/file.c
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/student-db $(1)/usr/bin/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))