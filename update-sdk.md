# Update the SDK

Through this guide, you will be introduced how to update the SDK if you already have installed the SDK previously. Please, restart the Editor before continuing.

## Remove Old Package

Remove the previous HISPlayer SDK package from Unity Package Manager.

**Window > Package Manager > Packages - HISPlayer > HISPlayer SDK > Remove**

<p align="center">
  <img width=80% alt="Remove" src="https://github.com/HISPlayer/UnityWebGL-SDK/assets/47497948/00071022-a78b-4b36-bd1d-eaf64aad49fc">
</p>

<br>

## Import New package

Importing the new package is the same as importing other normal packages in Unity. 
Select the package of HISPlayer SDK and import it.

**Assets > Import Package > Custom Package > HISPlayerSDK.unitypackage**

<p align="center">
<img width=60% src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/a094b781-03ef-4f12-bec1-868b713fc5eb">
</p>

<br>

## Configure Unity for visionOS

### Install the visionOS Unity package

Open the window **Window > Package Manager located in the upper side of the screen > Click on '+' > Add package by name** and write **com.unity.xr.visionos** in the box and wait until 
the package is installed.

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

</br>

<p align="center">
  <img width=70% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/bd28a63f-5622-48f2-84cf-88cc3d10e46d">
</p>

## Update License Key
If you received a license key from HISPlayer, please input the license key in the License Key field.

<p align="center">
<img width=70% alt="image" src="https://github.com/HISPlayer/UnityWebGL-SDK/assets/47497948/50b10c75-c6e0-438d-ba1f-da6e66d51eed">
</p>

If the license key is not valid, the player won’t work and will throw an error message. License key is not required for Unity Editor usage.
