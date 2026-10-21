# Quest-XSA - Reproducibility and validation plan

This repository documents a possible engineering architecture. The live source does not contain a complete Unity/Android/NDK project tree, signed Quest APK or independently reproduced thermal-plus-UV experiment.

## What can be reviewed now

The README, index.html and research.html provide architecture explanations, image-based concepts, illustrative pseudocode and proposed user interactions. The evidence classifications are documented in EVIDENCE_STATUS.md.

## Work required for a functional prototype

1. Record exact Quest headset model and firmware, Unity version, graphics API, Meta XR/OpenXR packages, Android target, USB hub and power supply.
2. Choose and identify a suitable LWIR module and confirmed USB-capable bridge. Record device descriptors, permission logs, frame formats and timestamps.
3. Separately choose a UV-sensitive detector with verified spectral range, UV-transmitting optics and filters. A USB Video Class camera alone is insufficient evidence of UV sensitivity.
4. Validate one sensor stream and texture using a minimal Quest application. Confirm graphics resource ownership and synchronization.
5. Measure simultaneous streams, USB bandwidth, hub power roles, dropped frames and independent arrival timestamps.
6. Calibrate each camera and rigid sensor-to-headset transformation. Measure held-out registration errors with uncertainty.
7. Report CPU/GPU frame timing, sensor-to-display latency, power, heat and user safety in repeatable trials.
8. Release test fixtures, permitted raw logs, build instructions and adverse observations only with appropriate rights clearance and author approval.

Primary engineering references:
- Android USB Host: https://developer.android.com/develop/connectivity/usb/host
- Meta experimental USB Video: https://github.com/facebookexperimental/usb-video
- FLIR Lepton: https://www.flir.com/products/lepton/
- Unity external textures: https://docs.unity3d.com/ScriptReference/Texture2D.CreateExternalTexture.html

All stages are proposed future verification, not results obtained in Quest-XSA.
