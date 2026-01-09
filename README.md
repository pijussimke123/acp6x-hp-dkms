# 🎤 AMD Yellow Carp Audio Patch

This patch fixes the audio driver selection logic in the Linux kernel, specifically addressing issues where the internal microphone array fails to register on supported hardware.

## 🔧 The Fix

* **Corrects Driver Selection:** By default, Board ID `15E2` (Revision 62) incorrectly loads the **Raphael** driver (`snd-rpl-pci-acp6x`), which is feature-incomplete and lacks microphone support. This patch forces the kernel to use the fully functional **Yellow Carp** driver (`snd-pci-acp6x`).
* **Enables Internal Microphone:** Successfully initializes the DMIC (Digital Microphone) array on affected OMEN devices.

## 💻 Compatibility

* **Validated Hardware:** HP OMEN 16 (Board ID `8E35`).
* **Technical Specifics:** Targets AMD Revision 62 of Board ID `15E2`.

## 🤝 Extending Support

This patch adds the OMEN 16 to the driver's quirk table. If you have a similar AMD-based laptop with non-functional microphones, you can easily add your own Board ID to the quirks list following the pattern established in this patch.
