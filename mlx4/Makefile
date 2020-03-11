include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk
include $(INCLUDE_DIR)/package.mk

PKG_NAME:=mlx4
PKG_VERSION:=0.1.0
PKG_RELEASE:=1

define KernelPackage/mlx4
  SUBMENU:=Network Devices
  TITLE:=Mellanox Technologies 1/10/40Gbit Ethernet support
  DEPENDS:=@PCI_SUPPORT
  FILES:= \
       $(LINUX_DIR)/drivers/net/ethernet/mellanox/mlx4/mlx4_core.ko \
       $(LINUX_DIR)/drivers/net/ethernet/mellanox/mlx4/mlx4_en.ko
  KCONFIG:= \
       CONFIG_MLX4 \
       CONFIG_MLX4_CORE=y \
       CONFIG_MLX4_CORE_GEN2=y \
       CONFIG_MLX4_DEBUG=y \
       CONFIG_MLX4_EN_DCB=y \
        CONFIG_MLX4_EN=y

  AUTOLOAD:=$(call AutoProbe,mlx4)
endef

define KernelPackage/mlx4/description
  Mellanox Technologies ConnectX Ethernet
endef

$(eval $(call KernelPackage,mlx4))

