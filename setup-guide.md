# Quick Start Guide
Getting started with HISPlayer consists of implementing the following steps:

1. Import and configure package   

      1.1. Import package
 
      1.2. Configure Unity for visionOS
   
2. Create your own sample
   
    2.1 Setup HISPlayer Manager
   
    2.2 Attach Unity Resources
   
    2.3 Configure HISPlayer Properties

    2.4 Build and Run

It's also possible to import the **HISPlayer visionOS Sample** after completing step 1.

Please, download the sample here -> [**HISPlayer visionOS Sample**](https://downloads.hisplayer.com/Unity/AllPlatforms/HISPlayer_Sample_3.3.1_Beta.unitypackage) (no need to download it if you have received it in the email).
The sample is a comprehensive example scene using the HISPlayerSDK to help demonstrate features like play, pause, seek, etc.

## 1.1 Import Package
Importing the package is the same as importing other normal packages in Unity. Select the package of HISPlayer SDK and import it.

**Assets > Import Package > Custom Package > HISPlayerSDK unity package**

<p align="center">
<img width=40% src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/a094b781-03ef-4f12-bec1-868b713fc5eb">
</p>


## 1.2 Configure Unity for visionOS

### Install the visionOS Unity package

Open the window **Window > Package Manager located in the upper side of the screen > Click on '+' > Add package by name** and write **com.unity.xr.visionos** in the box and wait until the package is installed.

<p align="center">
<img width=35% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/bb06febd-a942-4948-835d-5a6fe23e911a">
<img width=35% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/448a9ddd-495f-4d81-86f5-5878462dd270">
</p>

Open **Edit > Project Settings > XR Plug-in Management** select the visionOS platform and enable the option **Apple visionOS**

<p align="center">
  <img width=75% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/9d9c4fee-94ad-451a-ae7c-6a17ef58ae9e">
</p>

In the same window open **XR Plug-in Management > Project Validation** and click on **Fix All** button. If there is still some error on the panel follow the instructions until you have no errors.

<p align="center">
  <img width=75% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/f64b004f-452f-4f89-bf99-4b81f3472a5c">
</p>

### Install the PolySpatial Unity package

Open the window **Window > Package Manager located in the upper side of the screen > Click on '+' > Add package by name** and write **com.unity.polyspatial** in the box and wait until the package is installed. 

Please, after installing the package refer to [Mixed Reality](/mr-mode.md) to know how to use HISPlayer SDK within this mode.

<p align="center">
<img width=35% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/bb06febd-a942-4948-835d-5a6fe23e911a">
<img width=35% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/fda546ce-080d-4dcb-9a66-f1a283d51d51">
</p>

### Deploy for Apple Vision Pro Device

In the **Project** window, open **Packages > HISPlayer SDK > HISPlayer > Plugins > iOS** select HISPlayeriOS.framework and exclude visionOS platform.

<p align="center">
  <img width=75% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/8a1e9242-ed51-469c-b43f-7a7a33d8fdc0">
</p>

In the case of using the **Apple Vision Pro device**, please, follow these steps:
 
 - Open **Project** window open **Packages > HISPlayer SDK > HISPlayer > Plugins > visionOS**, select HISPlayerVisionOS.framework, exclude iOS and enable the option **Add to Embedded Binaries**.
 - Open **Packages > HISPlayer SDK > HISPlayer > Plugins > visionOS > simulator**, select select HISPlayerVisionOS.framework and exclude visionOS platform.

<p align="center">
  <img width=70% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/f29bdf62-22aa-4d3c-8788-e1914c7cfe23">
</p>

</br>

<p align="center">
  <img width=70% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/aa0cdd04-125a-4516-b84b-243607b06d03">
</p>


### Deploy for Apple Vision Pro Simulator

In the **Project** window, open **Packages > HISPlayer SDK > HISPlayer > Plugins > iOS** select HISPlayeriOS.framework and exclude visionOS platform.

<p align="center">
  <img width=75% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/8a1e9242-ed51-469c-b43f-7a7a33d8fdc0">
</p>

In the case of using the **Apple Vision Pro simulator** for Xcode, please, follow these steps:

 - Open **Project** window open **Packages > HISPlayer SDK > HISPlayer > Plugins > visionOS > simulator**, select HISPlayerVisionOS.framework, exclude iOS and enable the option **Add to Embedded Binaries**.
 - Open **Packages > HISPlayer SDK > HISPlayer > Plugins > visionOS**, select select HISPlayerVisionOS.framework and exclude visionOS platform.

<p align="center">
  <img width=70% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/900fa562-3765-40a6-9665-38d0a86e3079">
</p>

## 2.1 Set up HISPlayer Manager
*You may skip this section if you use [**HISPlayer visionOS Sample**](https://downloads.hisplayer.com/Unity/AllPlatforms/HISPlayer_Sample_3.3.3_Beta.unitypackage). The code set-up is already included in the sample script (HISPlayerController.cs).*

Create a new script which will inherit from **HISPlayerManager**, for example, visionOSStreamController. It is necessary to add the **'using HISPlayerAPI;'** dependancy. Then, add this component to a new game object (recommended to be empty).

Call the **SetUpPlayer()** function in order to initialize the stream environment internally. This function can be called whenever it’s needed.

For example, using the Awake function:

```C#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using HISPlayerAPI;

public class visionOSStreamController : HISPlayerManager
{
    protected override void Awake()
    {
        base.Awake();
        SetUpPlayer();
    }
}
```

It is strictly necessary to use SetUpPlayer before using anything else. This function initializes everything else that will be needed during the usage of HISPlayer APIs. 

Remember to call the Release function after closing the app or before changing scenes in Unity for freeing the internal resources. 

### 2.1.1 Mixed Reality mode
In order to use the Mixed Reality, please, copy the following code in your code. For more information, refer to [Mixed Reality](https://hisplayer.github.io/UnityVisionOS-SDK/#/mr-mode).

```C#
    protected override void EventVisionOSTextureUpdated(HISPlayerEventInfo eventInfo)
    {
        StreamProperties stream = multiStreamProperties[eventInfo.playerIndex];

        // Unity.PolySpatialObjectUtils.MarkDirty(renderTexture) is used to render correctly on Mixed Reality mode
        // Use the RenderTexture attached to the stream with index {eventInfo.playerIndex}"
       PolySpatialObjectUtils.MarkDirty(stream.renderTexture);
    }
```

## 2.2 Attach Unity resources

Move to **Unity Editor** to attach all the resources. The rendering system is supporting **Material** and **RenderTexture** Unity’s components. Raw Image is not available for a VR experience.

### <ins>RenderTexture</ins>
#### Virtual Reality Mode
In the case of **Virtual Reality** mode, please, refer to **Packages > HISPlayer SDK > Resources > Materials > HISPlayerDefaultMaterialRenderTexture.mat** and **Packages > HISPlayer SDK > Resources > RenderTextures > HISPlayerRenderTexture.renderTexture**. You can attach the HISPlayerDefaultMaterialRenderTexture.mat to the GameObject that is going to render the video content. Finally, attach HISPlayerRenderTexture.renderTexture to the stream controller component.

<p align="center">
<img width=90% src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/2d4e3196-16a5-4728-80b4-bf1b6ddbb5a8">
</p>

</br>

<p align="center">
<img width=90% src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/65615f47-bb39-4c8c-bf30-7db12490d3a2">
</p>

You can also create your own RenderTexture by clicking **Assets > Create > Render Texutre** and then create a **Material** referencing the **Render Texture**.

We recommend you to create your own shaders for the created material. Please, refer to  **Packages > HISPlayer SDK > Scripts > Shaders > HISPlayerDefaultShader.shader** 

#### Mixed Reality mode
In the case of **Mixed Reality** mode, please, import our [HISPlayer Sample](https://hisplayer.github.io/UnityVisionOS-SDK/#/./import-sample) and refer to **Assets > HISPlayerSample > Resources > visionOS-MR > HISPlayerVisionOSMRMaterial.material** and **Assets > HISPlayerSample > Resources > visionOS-MR > HISPlayerVisionOSMRRenderTexture.renderTexture**. You can attach the HISPlayerVisionOSMRMaterial.material to the GameObject that is going to render the video content. Finally, attach HISPlayerVisionOSMRRenderTexture.renderTexture to the stream controller component.

<p align="center">
<img width=90% src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/bb75e4ee-2524-4181-9470-74bc75663184">
</p>

</br>

<p align="center">
<img width=90% src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/c9342fdc-f0f1-4fec-97bc-716a8451760f">
</p>

You can also create your own RenderTexture by clicking **Assets > Create > Render Texutre** and then create a **Material** referencing the **Render Texture**.

We recommend you to create your own shaders for the created material. Please, refer to  **Assets > HISPlayerSample > Resources > visionOS-MR > HISPlayerVisionOSMRShader.shadergraph**.

## 2.3 Configure HISPlayer Properties
### <ins>License Key</ins>
Input the license key that is associated with the SDK. If the license key is not valid, the player won't work and will throw an error message. 
License key is not required for Unity Editor usage.

<p align="center">
<img width=70% src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/f6b00f15-92c3-4f40-ac0f-5b59f1c729f6">
</p>

### <ins>Multi Stream Properties</ins>
Use **Multi Stream Properties** to set all configurations needed for multi streams (not supported on Windows Editor). It starts with 0 elements. Each element added has its own configuration for multiple players and corresponds to 1 Render Surface. If you just need a single stream, then you just need to add 1 element with 1 URL.
* <span style="color:blue">**Render Mode**</span>: Select the render surface. It can be RenderTexture, Material, RawImage or NONE.
* <span style="color:blue">**Render Texture**</span>: Attach the **RenderTexture** to the **RenderTexture** section of the element.
* <span style="color:blue">**URL**</span>: Add the URL associated to the stream. Currently only single URL is supported.
* <span style="color:blue">**Autoplay**</span>: Property to determine whether the player will start automatically after set up.
  
<p align="center">
<img width=70% src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/449c713e-507b-4b9b-ad65-59d2ad3709c0">
</p>

## 2.4 Build and Run:
Once the configuration it’s done, open **‘Build Settings’** and press **‘Build And Run’**.

<p align="center">
<img src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/92c0764b-9a75-4916-9616-c6397b5d7824" width=60%>
</p>
