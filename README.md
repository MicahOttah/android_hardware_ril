# android_hardware_ril

Fork of `LineageOS/android_hardware_ril` with the changes of the **LG G
Pad X 8.0 (V521)** port to **LineageOS 15.1** (Android 8.1).

| Branch | What it is |
| --- | --- |
| `lineage-15.1` | the upstream LineageOS 15.1 branch, unchanged |
| `lineage-15.1-caf` | the branch the V521 port builds from |

## What is different on `lineage-15.1-caf`

| Commit | Subject |
| --- | --- |
| `904ec8a` | libril: fix the CAF SIM_IO payload, command mapping, signal strength and data registration |

The radio daemon of this device is the CAF `libril.so` blob, and the HIDL
RIL on the platform side has to speak its dialect:

* the **SIM_IO** request carries the CAF payload layout and the CAF command
  numbers, not the AOSP ones,
* the **signal strength** response has to be unpacked the CAF way, and
* the **data registration** request has to be answered with the *voice*
  registration state, because CAF does not implement the data registration
  request at all.

Without these three the radio registers for voice but the mobile data
never comes up.

## The port

The full description of the port is in the device tree:
<https://github.com/MicahOttah/android_device_lge_v521>
