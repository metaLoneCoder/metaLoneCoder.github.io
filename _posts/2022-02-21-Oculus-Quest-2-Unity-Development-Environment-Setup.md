---
layout: post
title: Oculus Quest 2 Unity Development Environment Setup
---

Unity 2020.3.29f1 **LTS** 
{: .message }

## Install Unity Editor

- Go to the Unity Download page, click Download Unity Hub, and then install it.
- On the Installs tab, click Add, and then select the Unity version from the list.
- In the Add modules to your install window, select Android Build Support, and then do the following:
1. Expand Android Build Support
2. Select Android SDK & NDK Tools and OpenJDK.


## Build Settings

It is recommend that you set the app’s target platform to Android, prior to performing any other project settings as there are a variety of settings that depend on it.

- In the menu, go to File and select Build Settings.
- Under Platform, select Android.
- Set Texture Compression to <mark>ASTC.</mark>

## Project Settings

- In Minimum API Level, set the minimum Android version to Android 6.0 Marshmallow (<mark>API level 23</mark>) for Oculus Quest 2.
-  In Target API Level, select Automatic (highest installed) to let the app support the highest Android version available.

## Enable Virtual Reality Support

With the Unity version 2019.3 and higher, Unity has introduced the XR plug-in framework, which allows Oculus to integrate with Unity’s engine and make full use of its features.
{: .message }

- From the menu, go to Edit > Project Settings.
- From the left navigation pane, select XR Plugin Management, and click <mark>Install XR Plugin Management.</mark>
- Click the Android tab and select Oculus to install the Oculus XR plugin, which enables the VR support.
- From the left navigation pane, under XR Plugin Management, click Oculus to open and modify the default settings.

## Set Rendering Preferences

- From the menu, go to Edit > Project Settings > Player, and select the Android tab.
- Expand Other Settings and under Rendering, do the following:
1. Set the Color Space property to <mark>Linear</mark> for realistic rendering.
2. Clear Auto Graphics API to manually pick and set the order in which the Graphics APIs are consumed. The Linear color space requires OpenGL ES 3.0 or Vulkan. Currently, Oculus Quest supports Vulkan but it is under experimental phase. Therefore, it is highly recommend that you use OpenGL ES 3.0 and set that as the first Graphics API in the order.
3. Select Multithreaded Rendering to move graphics API calls from the main thread to a separate worker thread.
4. Select Low Overhead Mode to skip error checking in release versions of an app. This is applicable to apps that use OpenGL ES API.

## Define Quality Settings

- In the menu, go to Edit > Project Settings > Quality.
- In Pixel Light Count, <mark>set the maximum number of pixel light count to one.</mark>
- In Texture Quality, select Full Res to display textures at maximum resolution.
- In Anisotropic Textures, <mark>select Per Texture.</mark>
- In Anti Aliasing, <mark>select 4x</mark>
- <mark>Clear the Soft Particles check box.</mark>
- Select Realtime Reflections Probes to update reflection probes during gameplay.
- Select Billboards Face Camera to force billboards to face the camera while rendering instead the camera plane.

## Generate Android Manifest File

Oculus has automated the process of adding the metadata in the manifest file and you need to generate the Android Manifest file from Unity.

- To generate the Oculus store-compatible Android manifest file, in the menu, go to Oculus > Tools > Create store-compatible AndroidManifest.xml.