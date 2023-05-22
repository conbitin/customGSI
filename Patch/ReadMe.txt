1. Copy vendor/ folder to device/ under the root Android directory.

2. Apply patch build_make_diff.patch to build/make project. Or add/replace following line into product make file

# Boot animation
PRODUCT_COPY_FILES += \
    device/vendor/config/bootanimation/bootanimation_fulgo.zip:/system/media/bootanimation.zip


3. Apply patch gereric_common_diff.patch to device/generic/common project. Or add following line into product make file

$(call inherit-product, device/vendor/config/device_fulgo.mk)

4. Apply launcher_changes.patch to packages/apps/Launcher3 project if device is using Android Launcher 3 as default Launcher. If device is using a different Launcher, please reorder hotseat as provided homescreen_layout.png

5. Apply apply_default_lock_wallpaper.patch under framework/base
