---
layout: post
title: Interact with Unity's Native UI using Laser Pointer (Oculus Quest 2)
---

**Oculus Quest 2 First Build (Controllers in 3D Space)** [Required](https://metalonecoder.github.io/2022/02/22/Oculus-Quest-2-First-Build/)
{: .message }

- Search UIHelpers
- Add UIHelpers prefab to scene
- <mark> Setactive Line Renderer </mark> in LaserPointer child of UIHelpers

<p align="center">
  <img src="/assets/images/21-02-23/1.PNG">
</p>

- In EventSystem -> OVR Input Module(Script) Drag RightHandAnchor in Ray Transform field

<p align="center">
  <img src="/assets/images/21-02-23/2.PNG">
</p>

- In Joy Pad Click Button set it to Secondary Index Trigger (Right Controller Index trigger)

<p align="center">
  <img src="/assets/images/21-02-23/3.PNG">
</p>

<br>

## Unity Native UI System

**Create Canvas**
- In Canvas set <mark> Render Mode </mark> to World Space
- Add CenterEyeAnchor as <mark> Event Camera.</mark>
- Add OVR Raycaster (Script) and Remove Graphic Raycaster
- Set Pointer to <mark> LaserPointer </mark>(UIHelpers)

<br>

**Adding Buttons**
- Add TMP (Import Text Mesh Pro Package) UI Button in the Scene

<br>

**Adding ScrollView**
- Add <mark> OVR Raycaster </mark> (Script)
- Remove Horizontal scrollbar
- Scroll Rect -> Movement Type to Clamped
- Scroll Sensitivity to 35
- Uncheck Inertia
- In Viewport -> Content add Grid Layout Group
- Add Content Size Filter 
- Set Horizontal Fit Unconstrained
- Set Vertical Fit Preferred Size
- Scroll view -> Viewport -> Content -> Add Buttons

<br>

**Adding Toggle** 
- Add Toggle Button to Canvas 
- Replace textView with TMP

<br>

**Adding DropDown**
- Add Dropdown to Canvas
- Set Options

<br>

## Unity Project 


`You can Download the Unity Project Files` [Here](https://github.com/metaLoneCoder/Pointer)
{: .message }

