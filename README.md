OseerArt (also known as TraceAR) is an Augmented Reality mobile application designed to help deaf and hard-of-hearing learners (and anyone who wants to improve their drawing skills) by overlaying traceable sketches onto real-world surfaces using a phone camera.
The app uses Unity’s AR Foundation to anchor sketches onto paper or flat surfaces, allowing users to trace over them easily.
Users can explore multiple categories of sketches — Nature, Animals, Architecture, and Sculptures — and interact with them using gestures to scale, move, and rotate the overlays in AR space.

**Key Features**

AR Sketch Projection — overlay reference sketches onto paper using the camera.

Category Selection — choose from Nature, Animals, Architecture, or Sculptures.

Dynamic Loading — load sketches from categorized folders dynamically.

Gesture Controls — pinch to zoom, rotate, or reposition the sketch overlay.

Accessible UI — designed for deaf and hard-of-hearing users with visual cues and clean layouts.

Dark Mode — adaptive dark/light themes for user comfort.

How to Set Up the Environment
1. Install Unity Hub

Download and install Unity Hub from the official Unity website.

2. Install Required Unity Version

Inside Unity Hub:

Add Unity version 6000.0.60f1 LTS

Make sure to include:

Android Build Support

iOS Build Support (optional)

Windows/Mac Build Support

3. Enable AR Foundation

In Unity:

Go to Window → Package Manager

Switch to Unity Registry

Install the following:

AR Foundation

ARCore XR Plugin (for Android)

ARKit XR Plugin (only if building for iOS)

Confirm AR Foundation packages are added to the project.

4. Configure Build Settings
For Android Builds:
A. Switch Platform

Go to File → Build Settings

Select Android

Click Switch Platform

B. Configure XR Plug-in

Go to Edit → Project Settings → XR Plug-in Management

Under Android, enable:

ARCore

Ensure ARCore Required is checked (if your app must run only on AR-capable devices).

C. Player Settings

Go to Edit → Project Settings → Player

Under Other Settings:

Set Minimum API Level to Android 8.0 (API Level 26) or higher.

Set Target API Level to Automatic (Highest Installed).

Scripting Backend = IL2CPP

Architecture = ARM64 (required by Google Play)

D. Enable Permissions

Unity automatically adds camera permission, but confirm:

Player Settings → Publishing Settings → “Custom Main Manifest” OFF
(Unless you manually modified manifest)

E. Connect Device

On your Android phone:

Enable Developer Options

Enable USB Debugging

Install ADB drivers if needed

Connect your device via USB

5. Configure Project for AR

Inside Unity:

Create an AR Session game object

Create an AR Session Origin game object
(This contains the AR Camera)

Verify:

AR Camera uses AR Camera Background

Tracking mode set to Position & Rotation

6. Clone the Repository

git clone https://github.com/OdinEM/traceAR.git


Then open the project through Unity Hub.

7. Import Assets

Add your Image Targets

Add your 3D Models, Quad Overlays, Materials, and UI Prefabs

Verify that your reference images are added inside the XR → AR Tracked Image Manager

8. Test the AR Scene

Open your AR scene (e.g., CameraScene)

Hit Build & Run

Point your device at the image target

Confirm initial material spawns correctly

Add a proper .gitignore for Unity
