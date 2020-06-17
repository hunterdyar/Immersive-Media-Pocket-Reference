---
layout: page
title: From Zero To Oculus Quest
nav_order: 3
parent: Guides
---
# Zero To Quest 

See videos for in-depth explanation and see below for a checklist refresher.

## Part 1 - Software Setup
<iframe width="560" height="315" src="https://www.youtube.com/embed/aRjNTpM06qc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Part 2 - Project Setup
<iframe width="560" height="315" src="https://www.youtube.com/embed/nSeXbIaacmc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Quest Setup
1. Make sure your Oculus account has an organization associated with it. Do this at [dashboard.oculus.com](dashboard.oculus.com).
2. Set your Oculus to Developer Mode. Do this from the Oculus app on your smart device.
   1. Sometimes this may end up getting disabled, so if things are not working, remember to come back and double check this.
3. Plug your Oculus into your computer and check "Allow USB Debugging" in the pop-up window, checking the "always allow" box.
4. If you are using a link cable, having Quest Link enabled should not affect sending builds to the device.

## Unity Setup
1. You need to have "Android Build Support" checked (and the drop down boxes for it checked too), under modules (in the drop down menu), for the unity version you are using.
   1. All of this can be found in the install section of the unity hub. You'll figure it out.

## Project Setup
1. Use the "3D" Template when creating a new project, don't use the High Definition Render Pipeline (HDRP) or Universal Render Pipeline (URP). *For now*.
1. Under File > Build Settings, switch the target platform to Android.
   1. Now you can "Build" to create a .apk file, or "Build and Run" to create the .apk and install it on a connected device. 
2. Install the "XR Plugin Management" package. 
3. Under "XR Plugin Management" in the project settings window (which is now available because this package is installed). 
   1. You want to add the appropriate loaders. For quest, check the box for the Oculus loader under the android tab.
   2. You may want to enable it under the desktop tab as well for Oculus Link/Rift S support.
4. I recommend using the XR Interaction Toolkit, which is (at the time of typing), a preview package.
   1. In Package Manger, select advanced > Show Preview Packages, and then install the XR Interaction Toolkit. 
   2. This gives you some easy rig creation options under the GameObject > XR menu.
5. You will likely want to "Seed Legacy Input Bindings" under the Assets menu.
   1. This is part of Legacy Input Helper package, which should be installed by default when you install "XR Plugin Management".
   2. This allows you to easily use the Input.GetAxis(""); and similar functions to get XR controller input data.

## Notes
   1. You don't need Unity to install the .apk onto the device. Building the apk and sending it to the device are independent processes. You can install it on the quest with [sidequest](sidequestvr.com) (graphical software) or [Android Developer Bridge](https://developer.android.com/studio/command-line/adb), command line tools.


---

## Using The Oculus Integration

If you want to use Hand Tracking, which is not currently supported with the above technique, you will need to use the "old" way of doing things. While out of date for Unity, Oculus has been updating their software integration for it.

1. The Quest and Unity setup is the same. 
2. Switch To Android Build Target before importing the oculus integration to save some time. (File> Build Settings).
3. Get the "[Oculus Integration](https://assetstore.unity.com/packages/tools/integration/oculus-integration-82022)" from the asset store. 
4. When you import it, the integration will have upgrade and restart the editor. I don't know why. It's a pain.
5. Go to Edit > Project Settings > Player, and scroll down to XR Settings. Check "Virtual Reality Supported".
6. To use Oculus Link and get in-editor (play mode) testing support, you may need to import the "Oculus Desktop" package from the package manager.
7. Look at sample scenes and use provided prefabs to get started.