# Quest-XSA independent research audit

Branch `research/preprint-audit-v1` forks main at `cdb582cd888afeca7b0387e181af19285cadad0a`.

Status: engineering feasibility analysis / systems integration proposal, NOT a tested Quest thermal/UV prototype.

Critical evidence boundaries:
- Repository README explicitly notes absence of a complete standalone Unity/Android/NDK application tree.
- Meta USB Video provides Quest 3 UVC capture precedent but not the proposed sensor integration.
- FLIR Lepton thermal modules deliver VoSPI over SPI and need a qualified USB bridge for the proposed path.
- UVC means USB Video Class, not ultraviolet wavelength detection.
- Project graphic ~25 FPS vs 72+ FPS is not supported by measurements.
- Spatial registration, simultaneous operation, latency, power and thermal stability have no validated Quest-XSA dataset.

Manuscript and extended claim/feasibility registers were prepared outside the live Pages assets. Publication and Zenodo deposition are withheld pending complete recursive repository/rights audit, exhaustive source checking, author declarations and approval.

Sources: https://oem.flir.com/products/lepton/ ; https://www.sony-semicon.com/en/products/is/industry/uv.html ; https://github.com/facebookexperimental/usb-video ; https://developer.android.com/develop/connectivity/usb/host
