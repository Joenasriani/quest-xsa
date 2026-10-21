# Quest-XSA - Technical evidence status

Source of record: GitHub main, assessed at commit cdb582cd888afeca7b0387e181af19285cadad0a.

Classification: Engineering design study and interactive guide. It is not a validated thermal or ultraviolet Quest headset prototype.

| Topic | Evidence category | Qualification |
| --- | --- | --- |
| Website, source documentation and diagrams | VERIFIED IMPLEMENTATION | Documentation exists; it is not a working device demonstration. |
| Thermal and UV sensor-to-headset architecture | DOCUMENTED DESIGN | Hardware, data flow and user interface proposed. |
| FLIR thermal camera via Android USB | TECHNICALLY PLAUSIBLE BUT UNTESTED | Specific board, transport bridge, permissions and frames not validated. |
| Genuine ultraviolet camera on Quest | TECHNICALLY PLAUSIBLE BUT UNTESTED | Detector spectral sensitivity, optics and acquisition not demonstrated. UVC means USB Video Class. |
| Unity and Android integration | DOCUMENTED DESIGN | Illustrative code; no complete compile-ready Unity project or validated native plugin. |
| Simultaneous thermal and UV data acquisition | UNSUPPORTED AS IMPLEMENTED | No dual-stream hardware tests or data records. |
| World-aligned multispectral overlays | DOCUMENTED DESIGN | No verified spatial calibration, synchronization or error figures. |
| Device FPS, latency, power and safety | UNSUPPORTED AS MEASURED | No Quest-XSA device-level benchmark or certification. |

The earlier numerical performance illustrations were not measured results. Current pages describe evaluation steps, not benchmark findings. See REPRODUCIBILITY.md for the proposed test plan.

Prior art includes Erickson et al. (2021), Beyond Visible Light, DOI: 10.1007/978-3-030-77599-5_23. Quest-XSA is not presented as the first thermal-plus-UV headset.

This file does not claim peer review, a released manuscript, a Zenodo DOI or third-party permissions.
