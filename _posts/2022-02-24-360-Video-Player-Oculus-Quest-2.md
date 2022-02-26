---
layout: post
title: 360 Video Player for Oculus Quest 2 (Using Unity SkyBox)

---

Unity 2020.3.29f1 **LTS**       
Oculus Integration **V37.0**
{: .message }

<br>

## Setup Unity Envirnoment for Oculus Quest 2 Development

- Set Up Unity Settings for Oculus Quest 2.
- Import Oculus Integration Package.
<br>

## Creating a Skybox Material

- In the Project window, right-click and select Create > Material

<p align="center">
  <img src="/assets/images/21-02-24/1.PNG">
</p>

- Select the Material you just created and in the Inspector, set the Shader to Skybox > Panoramic

<p align="center">
  <img src="/assets/images/21-02-24/2.PNG">
</p>

<br>

## Creating a Render Texture

- In your Project window, right-click and choose Create > Render Texture

<p align="center">
  <img src="/assets/images/21-02-24/3.PNG">
</p>

- Set the Render Texture so it will play at the correct resolution. If you already know the video resolution, Change the size parameter in your Render Texture to the correct dimensions. If you do not, you’ll need to find those dimensions in the Source Info panel.

<p align="center">
  <img src="/assets/images/21-02-24/4.PNG">
</p>

- Select your video in the Project window and click the video title in the bottom of the Inspector, next to the play button. Select Source Info. The video resolution is located in the Pixels row.

- Enter the values of your Render Texture in the Size box, starting with frame width.

- Finally, select your 360 Video Material, and set the newly created Render Texture as the Texture. You can do this by either dragging your Render Texture onto the Texture field or by clicking the Select button and searching for your new Render Texture.

<p align="center">
  <img src="/assets/images/21-02-24/5.PNG">
</p>

<br>

## Creating Video Player

- Create an Empty GameObject.

- Click your VideoPlayer GameObject and, in the Inspector window, click Add Component. In the search bar, type “Video” to find the VideoPlayer component.

- Leave the VideoPlayer GameObject selected in the Hierarchy window, and find your video in the Project window. Left-click and drag the video onto the Video clip box in the Inspector window.

- Find your Render Texture and drag it into the Render Texture slot on the Video Player component

<p align="center">
  <img src="/assets/images/21-02-24/6.PNG">
</p>

<br>

## Setting Skybox Material

- Select Window > Rendering > Lighting Settings to access the settings for the Scene’s Skybox.

- Drag your Skybox Material onto the Skybox Material slot under Environment. You can also click the widget to the right of Skybox Material and search for your Material there.

<p align="center">
  <img src="/assets/images/21-02-24/7.PNG">
</p>

- When you enter Play Mode, you should see the 360 Video appear in the viewport.

<br>

## Adding VR Camera

- Search for OVRCameraRig in Assets and add it to Scene.

- Build and Run.