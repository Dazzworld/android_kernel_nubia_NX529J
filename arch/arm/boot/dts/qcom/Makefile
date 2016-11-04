ifeq ($(CONFIG_OF),y)

dtb-$(CONFIG_ARCH_MSM8916) += msm8952-NFound.dtb

#DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM_APPENDED_DTB_IMAGE_NAMES))
CONFIG_BUILD_ARM64_APPENDED_DTB_IMAGE_NAMES=$(ZTEMT_DTS_NAME)
$(warning mhx$(CONFIG_BUILD_ARM64_APPENDED_DTB_IMAGE_NAMES))
DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM64_APPENDED_DTB_IMAGE_NAMES))

ifneq ($(DTB_NAMES),)
DTB_LIST := $(addsuffix .dtb,$(DTB_NAMES))
else
DTB_LIST := $(dtb-y)
endif

targets += dtbs
targets += $(addprefix ../, $(DTB_LIST))
endif

$(obj)/../%.dtb: $(src)/%.dts FORCE
	$(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(DTB_LIST))

clean-files := *.dtb
