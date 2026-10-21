# Quest-XSA: verified technical amendments (21 October 2026)

**Status:** research evidence annex; no Quest-XSA device demonstration claimed. Source project snapshot: main commit cdb582cd888afeca7b0387e181af19285cadad0a. Experimental branch modifies the webpage but not published Pages.

## Primary technical evidence and precise claim boundaries

1. **Quest 3 UVC capture precedent, external demonstration:** Meta experimental USB Video reports capture-card operation on Quest 2 and Quest 3. This is NOT evidence of the Quest-XSA thermal or UV camera operating, nor proof of simultaneous passthrough, USB inputs and Unity output. https://github.com/facebookexperimental/usb-video
2. **Android host APIs:** USB device enumeration, permission, interface and endpoint use depend on the target app and actual peripheral. An `android.hardware.usb.host` manifest entry is not itself authorization. https://developer.android.com/develop/connectivity/usb/host
3. **Thermal sensor transport:** FLIR Lepton 3.5 is a thermal sensor core, not a generic plug-in USB UVC camera. The design requires an identified electronics bridge or product with a verified application-facing USB protocol, buffer representation, radiometric interpretation and timing. Manufacturer support index: https://www.flir.eu/support/products/lepton/
4. **True UV sensing:** Sony specifies IMX487 detector sensitivity from 200 to 400 nm; this is a detector datasheet, not a qualified USB camera or validated Quest solution. Confirm optics, filters, illumination, spectral calibration and UV exposure risk. https://www.sony-semicon.com/en/products/is/industry/uv.html
5. **Texture integration:** Unity `Texture2D.CreateExternalTexture` wraps an externally allocated graphics object only where native type, dimensions, format and API agree. Actual upload, fences/context ownership and synchronization must be implemented and tested; zero-copy must not be inferred. https://docs.unity.cn/2022.3/Documentation/ScriptReference/Texture2D.CreateExternalTexture.html

## Source corrections now committed on research branch

- Main-page comparison ~25 versus 72+ FPS replaced with 'Unmeasured'. Additive ~35 +20 +10 +7 FPS optimization illustration converted to nonnumeric hypotheses. Neither before nor after was a measured Quest-XSA result.
- CPU-copy and native-texture diagrams changed to note uncertain performance and synchronization.
- Generic 'UV camera module' now identified as unselected, with spectral/optical verification requirements.
- USB permissions and JNI bridge descriptions expanded; the HTML C# fragment remains marked illustrative.
- A 2025 citation year tag removed pending author-supported provenance. Webpage update, research inception and future preprint first release are separate dates.

## Feasibility gates for physical validation

| Gate | Needed evidence | Status |
| --- | --- | --- |
| Quest USB host and specific VID/PID access | USB descriptors, permission flow, device logs | UNKNOWN for candidate sensors |
| LWIR-to-USB adapter | exact model, electrical wiring, firmware/protocol, raw frames | UNKNOWN |
| UV spectral acquisition | identified detector, bandpass, lens transmissions, UV/visible discrimination | UNKNOWN |
| Simultaneous thermal+UV streaming | two streams with timestamps over chosen hub | UNKNOWN |
| Unity textures | graphics API mapping, resource lifetime, buffer synchronization, logs | UNKNOWN |
| Spatial registration | camera-to-headset extrinsics, timestamp synchronization, calibration residuals | UNKNOWN |
| Safe sustained use | load, power/charge, device heat, illumination and exposure analysis | UNKNOWN |
| Measured performance | headset/app versions, frame timing and end-to-end sensor-to-photon latency | NOT MEASURED |

## Reproducible staged verification protocol

A. Record headset model, firmware, Android runtime, Unity version, Meta XR/OpenXR packages, USB hub and power configuration.
B. Validate one known UVC camera on Quest using a minimal Android test app; save descriptors, permission outcome, observed formats and timestamps.
C. Qualify LWIR input on an intermediate development host with sensor serial/model, adapter design and raw frames; then test Quest USB transfer.
D. Qualify the UV optical chain using traceable manufacturer spectral response and a controlled comparison against a visible-only camera. Do not use unsafe illumination without trained safety review.
E. Implement per-stream acquisition and log monotonic acquisition/arrival timestamps, loss and reconnect events.
F. Render a synthetic marked texture in Unity, then one sensor and finally both sensors in passthrough; profile upload/synchronization time and headset frame timing.
G. Calibrate external camera intrinsics and rigid-body extrinsics with independent held-out targets; quantify pixel/angle registration errors with uncertainty.
H. Repeat fixed-duration tests, declaring acceptance thresholds *before* measurement; publish raw logs, processing script, test versions, adverse observations and reproducible build instructions.

## Attribution and publication gates

The existing `CITATION.cff` is project-level software metadata; it does not prove a releasable software build. The proposed preprint has sole author Joseph Ribal Nasr and affiliation Independent Researcher. Image rights and first-publication dates remain unverified. No Zenodo release, DOI, peer review, device demonstration or rights clearance is implied.

This annex supplements, but does not claim to finish, the systematic literature review or exhaustive recursive asset inventory.
