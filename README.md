# linux-ycrcb-edid
Linux patches based on 4.17-rc4 that force a generic 1920x1080 EDID for YCbCr output.

The second patch hacks the DRM system to fix EDID read error when using generic
hardcoded EDID.

This is to fix amdgpu (AMD Ryzen 2200g with Vega graphics) EDID read errors and support a TV that has issues working with RGB HDMI signals.

To enable:
  Edit /etc/defult/grub:
    Change the Linux boot cmdline to include drm_kms_helper.edid_firmware=edid/1920x1080.bin
    
    e.g. GRUB_CMDLINE_LINUX_DEFAULT="quiet splash drm_kms_helper.edid_firmware=edid/1920x1080.bin"
  
  Run:
    sudo update-grub
 
