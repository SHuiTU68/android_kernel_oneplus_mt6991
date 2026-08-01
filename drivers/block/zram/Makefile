# SPDX-License-Identifier: GPL-2.0-only
zram-y	:=	zcomp.o zram_drv.o

obj-$(CONFIG_ZRAM)	+=	zram.o

# zram swap 保后台配置脚本 (init.rc 片段)
# 输出到 $(objtree)/drivers/block/zram/zram_init.rc, 供 ramdisk 打包流程拾取
always-$(CONFIG_ZRAM) += zram_init.rc

$(obj)/zram_init.rc: $(src)/init.zram_oplus.rc FORCE
	$(call if_changed,copy)
targets += $(obj)/zram_init.rc
