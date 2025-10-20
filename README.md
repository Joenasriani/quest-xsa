# innov-quest-xsa
A Framework for eXtensible Sensory Augmentation in Mixed Reality
Quest-XSA: A Framework for eXtensible Sensory Augmentation in Mixed Reality
​A comprehensive Unity framework for integrating external, non-standard camera sensors (e.g., thermal and UV) with the Meta Quest 3. This project provides a high-performance, real-time pipeline for augmenting human perception by rendering invisible light spectra as visual overlays in a mixed reality environment.
​Core Features
​Real-Time Sensor Streaming: A robust native Android plugin that interfaces directly with external UVC-compliant USB cameras.
​High-Performance GPU Pipeline: Utilizes a native texture pointer method to transfer video frames directly on the GPU, achieving 72+ FPS by eliminating CPU-bottlenecks.
​Modular Custom Shaders: A collection of shaders to simulate various animal vision modes, including Thermal (pit viper), UV (bee), and Enhanced Acuity (eagle).
​World-Space UI: An intuitive in-world user interface built with UI Toolkit for seamless interaction and mode switching using Quest controllers.
​Comprehensive Optimization: Implements critical mobile VR performance techniques, most notably Fixed Foveated Rendering (FFR), to ensure a smooth and comfortable user experience.
​System Architecture Overview
​The framework is built on a multi-layered architecture designed for maximum performance and modularity.
​Hardware Layer: External sensors (FLIR Lepton 3.5, X-Nite UV Camera) connect to a powered USB-C hub.
​Connectivity Layer: The hub connects to the Meta Quest 3's USB-C port.
​OS & Native Plugin Layer: A custom Android (.aar) plugin, built in Android Studio, uses the Android USB Host APIs to detect, request permissions for, and manage the raw data stream from the UVC devices.
​High-Performance Bridge (C++/NDK): The core of the plugin decodes the video stream directly into a native OpenGL texture on the GPU. It passes only the lightweight integer pointer (Texture ID) across the JNI bridge to Unity.
​Unity Engine Layer: C# scripts in Unity receive the texture pointer and use Texture2D.CreateExternalTexture() to reference the native GPU texture without copying pixel data.
​Rendering & Composition Layer: The texture is processed in real-time by custom vision shaders and rendered onto a 3D quad, which is composited over the live passthrough feed from the Quest 3's built-in cameras.
​Hardware Requirements
​The following components are required to replicate this project.
