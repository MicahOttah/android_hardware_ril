# android_hardware_ril

Fork of `LineageOS/android_hardware_ril` for the **LG G Pad X 8.0 (V521)**
LineageOS 15.1 port.  The port builds from `lineage-15.1-caf`; the other
branches are upstream.

Changes:

* libril speaks the CAF dialect of the stock `libril.so` blob: the CAF
  SIM_IO layout and command numbers, CAF signal strength, and the voice
  registration state as the answer to data registration.  Without this,
  mobile data never comes up.

Port and device tree: <https://github.com/MicahOttah/android_device_lge_v521>
