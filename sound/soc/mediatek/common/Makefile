#
# Copyright (C) 2015 MediaTek Inc.
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License version 2 as
# published by the Free Software Foundation.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
# GNU General Public License for more details.
#

# Old kernel architecture
MTK_PLATFORM := $(subst ",,$(CONFIG_MTK_PLATFORM))
subdir-ccflags-y += -Werror -I$(srctree)/drivers/misc/mediatek/include
subdir-ccflags-y += -Werror -I$(srctree)/drivers/misc/mediatek/include/mt-plat/$(MTK_PLATFORM)/include
subdir-ccflags-y += -Werror -I$(srctree)/drivers/misc/mediatek/include/mt-plat
obj-y += mtk-auddrv-devtree-parser.o
obj-y += mtk-auddrv-underflow-mach.o

# btcvsd
obj-$(CONFIG_MTK_BTCVSD_ALSA) += mtk-soc-pcm-btcvsd.o mtk-soc-pcm-btcvsd-rx.o mtk-soc-pcm-btcvsd-tx.o

# New kernel architecture
ifeq ($(CONFIG_MTK_SND_SOC_NEW_ARCH),y)

# Feature support
ifeq ($(CONFIG_MTK_TINYSYS_SCP_SUPPORT),y)
ccflags-y += -I$(srctree)/drivers/misc/mediatek/audio_ipi/$(MTK_PLATFORM)
ccflags-y += -DMTK_AURISYS_PHONE_CALL_SUPPORT
ccflags-y += -DMTK_AUDIO_TUNNELING_SUPPORT
endif

# Common object
obj-y += mtk-auddrv-afe.o mtk-auddrv-gpio.o
obj-y += mtk-soc-afe-control.o mtk-soc-pcm-common.o
obj-$(CONFIG_MTK_OFFLOAD_PLAYBACK) += mtk-soc-offload-common.o
obj-y += mtk-soc-pcm-capture.o mtk-soc-pcm-dl1.o mtk-soc-pcm-dummy.o mtk-soc-pcm-routing.o mtk-soc-pcm-capture2.o mtk-soc-pcm-i2s2-adc2.o
obj-y += mtk-soc-pcm-voice-md1.o mtk-soc-pcm-voice-md2.o mtk-soc-pcm-voice-md1-bt.o mtk-soc-pcm-voice-md2-bt.o
obj-y += mtk-soc-pcm-dl1-i2s0.o mtk-soc-pcm-dl1-i2s0Dl1.o mtk-soc-pcm-i2s0-awb.o
#obj-y += mtk-soc-pcm-hdmi.o
obj-y += mtk-soc-pcm-uldlloopback.o mtk-soc-pcm-dl2.o mtk-soc-pcm-mod-dai.o
#obj-y += mtk-soc-pcm_anc.o
#obj-y += mtk-soc-pcm-voice-ultra.o
obj-y += mtk-soc-pcm-mrgrx.o mtk-soc-pcm-mrgrx-awb.o mtk-soc-pcm-fm-i2s.o mtk-soc-pcm-fm-i2s-awb.o
obj-y += mtk-soc-pcm-dl1-awb.o mtk-soc-pcm-dl1-bt.o mtk-soc-pcm-bt-dai.o
obj-y += mtk-soc-dai-stub.o mtk-soc-dai-routing.o mtk-soc-codec-dummy.o mtk-soc-pcm-fmtx.o mtk-soc-tdm-capture.o
obj-y += mtk-soc-pcm-hp-impedance.o
obj-y += mtk-soc-machine.o

endif
