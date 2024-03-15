# Mixed Reality mode

For using **Mixed Reality** with Unity, the **[PolySpatial](https://docs.unity3d.com/Packages/com.unity.polyspatial.visionos@0.1/manual/index.html)** package must be imported in your project.

If you don't have the package in your project, please, open the window **Window > Package Manager located in the upper side of the screen > 
Click on '+' > Add package by name** and write **com.unity.polyspatial** in the box and wait until the package is installed.

<p align="center">
<img width=35% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/bb06febd-a942-4948-835d-5a6fe23e911a">
<img width=35% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/fda546ce-080d-4dcb-9a66-f1a283d51d51">
</p>

You can select the Mixed Reality mode by **Edit > Project Settings > XR Plug-in Management > Apple visionOS > App Mode > Mixed Reality - Volume or Immersive Space**. 

<p align="center">
<img width=70% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/10926ad5-6efe-4f47-ac54-27a18d371633">
</p>

If you haven't installed PolySpatial package yet, Unity will ask you to do it.

<p align="center">
<img width=70% alt="image" src="https://github.com/HISPlayer/UnityVisionOS-SDK/assets/47497948/bcb507e9-398a-4771-8325-a997a2a77409">
</p>

## HISPlayer SDK and Mixed Reality mode
Once you have installed the PolySpatial package, please, refer to [EventVisionOSTextureUpdated](https://hisplayer.github.io/UnityVisionOS-SDK/#/hisplayer-api?id=protected-virtual-void-eventvisionostextureupdatedhisplayereventinfo-eventinfo).
 This event is triggered when the RenderTexture used to rendering the video is updated. 

Override the function in your code and call the **protected virtual void EventVisionOSTextureUpdated(HISPlayerEventInfo eventInfo)** API and call the 
[**Unity.PolySpatial.PolySpatialObjectUtils.MarkDirty(renderTexture)**](https://docs.unity3d.com/Packages/com.unity.polyspatial@1.1/api/Unity.PolySpatial.PolySpatialObjectUtils.html) API to 
allow the rendering in the Mixed Reality mode. The 'renderTexture' parameter is the one attached to the stream with the index **eventInfo.playerIndex**.

You can use the following fragment code:

```C#
    protected override void EventVisionOSTextureUpdated(HISPlayerEventInfo eventInfo)
    {
        StreamProperties stream = multiStreamProperties[eventInfo.playerIndex];

        // Unity.PolySpatialObjectUtils.MarkDirty(renderTexture) is use to render correctly on Mixed Reality mode
        // Use the RenderTexture attached to the stream with index {eventInfo.playerIndex}"
       PolySpatialObjectUtils.MarkDirty(stream.renderTexture);
    }
```


