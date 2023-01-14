---
title: "Autofocus camera on Vuforia SDK Unity"
description: Autofocus camera on Vuforia SDK with Unity
frase: Vuforia is an augmented reality software development kit for mobile devices that enables the creation
tags:
  - Vuforia
  - Unity
  - AR
category: Vuforia
coverImage: vuforia-sdk.jpg
alt: vuforia sdk logo
date: 2022-12-03 16:22:52
---

## What is Vuforia?
Vuforia is an augmented reality software development kit for mobile devices that enables the creation of augmented reality applications. It uses computer vision technology to recognize and track planar images and 3D objects in real time.

Because Vuforia is an SDK, we need tools that can be used to make augmented reality apps. There is two tools that can be used with Vuforia SDK. Android Studio and Unity3D.

You can download Vuforia SDK for free from its official website [Vuforia SDK](https://developer.vuforia.com/)

## Autofocus camera on Vuforia AR
For this case, on vuforia it self there is no autofocus except for those have an expensive android phone or iphone, We can easily forced camera phone to autofocus.

First, you can make new script 

``
CameraFocusController.cs
``

Add using vuforia to import Vuforia SDK from library

``
using Vuforia;
``
Lets add camera focus function

``
void Start() {    
  var vuforia = VuforiaARController.Instance;    
  vuforia.RegisterVuforiaStartedCallback(OnVuforiaStarted);    
  vuforia.RegisterOnPauseCallback(OnPaused);
 }  

 private void OnVuforiaStarted() {    
  CameraDevice.Instance.SetFocusMode(
      CameraDevice.FocusMode.FOCUS_MODE_CONTINUOUSAUTO);
 }

 private void OnPaused(bool paused) {    
  if (!paused) // resumed
  {
       // Set again autofocus mode when app is resumed
       CameraDevice.Instance.SetFocusMode(
       CameraDevice.FocusMode.FOCUS_MODE_CONTINUOUSAUTO);    
  }
 }
}
``
Then you can add ``CameraFocusController.cs`` to ARCamera object. That's it!

[Repository Github](https://github.com/abimanyudrmwn/auto-focus-vuforia)
