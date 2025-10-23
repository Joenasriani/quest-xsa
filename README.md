# Quest-XSA: A Research Guide to Enabling Thermal,l and UV Vision on the Meta Quest

---


by @QuestReQuestVR (JOENASR)
> https://linktr.ee/questrequestvr


---

Link: 
> https://joenasriani.github.io/quest-xsa/

---


DESCRIPTION

Quest-XSA is an open-source guide detailing an invention that enables you to see the world in new light frequencies through the Meta Quest 3. This project walks you through integrating external thermal and UV cameras to create real-time, augmented reality overlays, effectively adding new senses to your perception. This repository contains all the necessary code, hardware lists, and step-by-step instructions.

---

CORE FEATURES

- Live Thermal & UV Vision: A robust system to stream real-time video from external sensors directly into the Quest 3.
- Fluid, High-Frame-Rate Experience: Utilizes a high-performance GPU pipeline to achieve 72+ FPS, ensuring a smooth and comfortable MR experience.
- Simulated Animal Senses: Includes custom shaders that transform raw sensor data into visualizations of Thermal (pit viper) and UV (bee) vision.
- Complete Project Guide: From hardware assembly to final deployment, this guide covers every step of the invention.

---

THE TECHNOLOGY EXPLAINED

This invention works by creating a high-performance bridge between external USB cameras and the Unity engine running on the Quest 3.

1. Hardware Layer: External sensors (FLIR Lepton, X-Nite UV Camera) are connected to the headset via a powered USB-C hub.
2. The Android & Native Plugin Bridge: A custom Android plugin uses the device's USB Host APIs to manage the raw data stream from the cameras.
3. High-Performance Data Transfer: The core of this invention is a C++/NDK layer that decodes video directly into a native OpenGL texture on the GPU. Instead of sending large, slow video frames to the CPU, it passes only a tiny, lightweight texture pointer to Unity.
4. Unity Engine Rendering: C# scripts in Unity use this pointer to directly access the GPU texture. The data is then processed in real-time by custom shaders and composited over the live passthrough feed.

---

HARDWARE REQUIREMENTS

To build this invention, you will need:

| Component                 | Recommended Model                  | Purpose                                              | Est. Cost (AED) |
| ------------------------- | ---------------------------------- | ---------------------------------------------------- | --------------- |
| VR Headset                | Meta Quest 3                       | The primary mixed reality platform.                  | ~1,835 AED      |
| Thermal Camera            | Teledyne FLIR Lepton 3.5           | Captures radiometric thermal data.                   | ~605 AED        |
| Breakout Board            | Lepton Breakout Board V2.0         | Interfaces the Lepton module with USB.               | ~245 AED        |
| UV Camera                 | XNiteUSB2S-MUV                     | UVC-compliant for driverless Android operation.      | ~550 AED        |
| UV Flashlight             | 365nm UV LED Flashlight            | Illuminates surfaces to reveal UV patterns.          | ~220 AED        |
| Powered Hub               | USB-C Hub with Power Delivery (PD) | Connects all devices and charges the headset.        | ~275 AED        |
| Total Estimated Cost      |                                    |                                                      | ~3,730 AED      |

---

GETTING STARTED: A STEP-BY-STEP GUIDE

1. Environment Setup:
   - Install Unity Hub and a recent Unity Editor (2023.1+ LTS).
   - Add the 'Android Build Support' module to your Unity installation.

2. Project Setup:
   - Clone the repository: `git clone https://github.com/your-username/Quest-XSA.git`
   - Open the project in Unity and switch the platform to 'Android'.
   - Run the Meta XR Project Setup Tool (`Meta XR > Tools`) and apply all recommended fixes.

3. Build & Deploy:
   - Enable Developer Mode on your Meta Quest 3.
   - Connect the headset via USB-C and accept the "Allow USB debugging" prompt.
   - In Unity, go to `File > Build and Run` to deploy the app. Find it in your App Library under "Unknown Sources".

---

FUTURE POSSIBILITIES

This invention is a platform for further exploration. Future work could include:
- Sensor Fusion (MSX): Overlaying passthrough camera edges onto the thermal image for enhanced detail.
- Data Logging: Recording sensor streams for scientific analysis.
- New Sensory Modalities: Adapting the architecture to visualize polarized light or magnetic fields.

---

CONTRIBUTING

Contributions are welcome. Please fork the repository and submit a pull request. For major changes, open an issue first.

---

LICENSE

A Research Project @QuestReQuestVR
https://linktr.ee/questrequestvr
(Joe Nasr)

