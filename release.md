# HISPlayer Unity visionOS SDK Release Notes

### Version 4.3.1
##### August 8, 2024
- [**Added**] New HISPlayer Video Uploader feature. Turn local videos into streaming videos such as HLS or DASH. This videos are going to be stored in our server for you. Please, on the Editor refer to:
    - [HISPlayer Video Upload documentation](https://hisplayer.github.io/UnityVideoUpload/#/)
- [**Improvement**] Optimized Event and Error listeners
- [**Improvement**] Optimized license checking
- [**Improvement**] Optimized HISPlayer API function commentaries to be more clear
- [**Improvement**] Optimized runtime log messages

### Version 3.4.2
##### April 24, 2024
- [**Added**] Custom resources to support the stereoscopic rendering mode for the VR mode.
  - HISPlayerStereoscopicShader.shader
  - HISPlayerStereoscopicMaterial.mat
  - HISPlayerStereoscopicRenderTexture.rendertexture
- [**Added**] Custom resources to play 180/360 videos.
  - HISPlayer180Material.mat
  - HISPlayer360Material.mat
  - HISPlayer180RenderTexture.rendertexture
  - HISPlayer360RenderTexture.rendertexture

### Version 3.4.1
##### April 23, 2024
- [**Improvement**] Improvement of software robustness

### Version 3.4.0
##### April 10, 2024
- [**Added**] HISPlayer360Shader.shader for the 360 VR mode
- [**Added**] HISPLAYER_ERROR_PLATFORM_NOT_REGISTERED error event

### Version 3.3.3
##### March 15, 2024
- [**Added**] visionOS Mixed Reality support.

### Version 3.3.2
##### March 5, 2024
- Software robustness improvement.

### Version 3.3.1
##### February 22, 2024
- Initial release of visionOS SDK Beta. The visionOS SDK is part of multiplatform SDK.
