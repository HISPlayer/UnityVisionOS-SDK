# Import HISPlayer visionOS Sample

Please, download the sample here -> [**HISPlayer visionOS Sample**](https://downloads.hisplayer.com/Unity/visionOS/HISPlayer_visionOS_Sample.unitypackage) 
(no need to download it if you have received it in the email).

Importing the package is the same as importing other normal packages in Unity. Select the downloaded package and import it.

- **Assets > Import Package > Custom Package > HISPlayer_Sample.unitypackage**

<p align="center">
  <img width=50% src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/9cddf00f-9abc-4075-9bc2-ba278b92a7f9">
</p>

- Complete the configuration for visionOS ->  [**Configure Unity for visionOS**](https://hisplayer.github.io/UnityVisionOS-SDK/#/setup-guide?id=_12-configure-unity-for-visionos)
  - To deploy for VisionPro device, please refer to the following configuration : [**Deploy for VisionPro Device**](https://hisplayer.github.io/UnityVisionOS-SDK/#/setup-guide?id=deploy-for-apple-vision-pro-device)
  - To deploy for VisionPro simulator, please refer to the following configuration : [**Deploy for VisionPro Simulator**](https://hisplayer.github.io/UnityVisionOS-SDK/#/setup-guide?id=deploy-for-apple-vision-pro-simulator)

- Open the scene **Assets/HISPlayerSample/Scenes/HISPlayerSampleMR.unity or HISPlayerSampleVR.unity**
   - HISPlayerSampleMR.unity is made for Mixed Reality experience
   - HISPlayerSampleVR.unity is made for Virtual Reality experience

<p align="center">
  <img width=60% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/bf6c58b9-c12d-44ad-b9bc-79ad32253950">
</p>

- Import TextMesh Pro Essential

- Input the license key through the Inspector.
  - VR Mode: **HISPlayerController** GameObject -> **HISPlayerVRController** component -> **License Key**
  - MR Mode: **HISPlayerController** GameObject -> **HISPlayerMRController** component -> **License Key**

<p align="center">
  <img width=80% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/83d30e56-f1e2-4fdb-be27-4834e12a842f">
</p>

- Open **File** > **Build Settings** > **Add Open Scenes**. 
<p align="center">
  <img width=70% alt="macos" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/d2d5489a-cdea-4abe-ae1c-f55b7deb069b">
</p>

- Review that the scene you want to run is correctly configured. Please, open **Player Settings > XR Plug-in Management > Apple visionOS > App Mode** and select:
   - **Virtual Reality - Fully Immersive Space** for **HISPlayerSampleVR.unity**
   - **Mixed Reality - Volume or Immersive Space** for **HISPlayerSampleMR.unity**

- Build and Run

To check how to set up the SDK and API usage, please refer to:
  
  - VR Mode: **Assets/HISPlayerSample/Scripts/HISPlayerVRController.cs** and **HISPlayerController GameObject** in the Editor.
  - MR Mode: **Assets/HISPlayerSample/Scripts/HISPlayerMRController.cs** and **HISPlayerController GameObject** in the Editor.

## UI Demo
The UI components in the HISPlayerSampleVR.unity are fully modifiable and each stream has its own UI. The sample is intended to show a comprehensive scene using the HISPlayer SDK to help demonstrate features such as play, pause, seek, etc using the multi stream feature. 

<p align="center">
  <img width=55% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/7b426d46-ab9f-4615-9159-74807ce98056">
</p>

<p align="center">
  <img width=90% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/f7662f44-28df-4e70-973b-7b7320eb712a">
</p>

## Add/Remove Streams and URLs
In order to add/remove streams and URLs, please refer to the component **HISPlayerVRController** attached to the **HISPlayerController GameObject** in the **Inspector** within the **HISPlayerSampleVR.unity** scene. 

### Add/Remove Streams

You can add/remove streams by pressing the buttons **+/-** in the **Multi Stream Properties list**. Once a new stream is added, please, select the RenderTexture mode and the RenderTexture surface where you want to display your videos. 

<p align="center">
  <img width=70% alt="streams" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/f0a1521d-807a-48f5-893e-58135516b37e">
</p>

<p align="center">
  <img width=70% alt="render-mode" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/e65f23af-cf95-4858-b654-d0199feecd71">
</p>

### Change URL
To change the default video URL using your own URL, please replace the element value with your own URL in the **URL list** of the stream you want to modify.

<p align="center">
  <img width=60% alt="replace-url" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/5b876db4-f3c9-4c98-84df-f23737070f50">
</p>

### Add/Remove URLs

You can add/remove URLs by selecting one element from the **Multi Stream Properties list** and then pressing the buttons **+/-** in the **Url list**. 
For changing the content of the videos, please refer to **[ChangeVideoContent](https://hisplayer.github.io/UnityVisionOS-SDK/#/hisplayer-api?id=protected-void-changevideocontentint-playerindex-int-urlindex)** API.

<p align="center">
  <img width=70% alt="add-url" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/b65bf99f-202b-436e-a9c3-f1a6b9b97eaa">
</p>

