# HISPlayer Unity Windows SDK Release Notes

### Version 4.10.0
##### September 11, 2025
- [**Improvement**] Editor no longer clears console logs after stopping Play mode.
- [**Improvement**] Improved log when releasing player.
- [**Improvement**] Improved package architecture for multiple packages combination.

### Version 4.9.0
##### July 10, 2025
- [**Improvement**] Optimized performance when a video restarts with loop option.

### Version 4.8.0
##### July 7, 2025
- [**Improvement**] Enhancement to InspectorGUI to dynamically show/hide certain options.

### Version 4.6.0
##### January 16, 2025
- [**Improvement**] Removed D3D11 warning messages.

### Version 4.5.0
##### December 4, 2024
- [**Improvement**] Optimized the event callbacks after removing streams.

### Version 4.4.2
##### October 16, 2024
- [**Improvement**] Optimized the video streams removal process.

### Version 4.4.0
##### September 10, 2024
- [**Added**] Release API is called automatically when stopping the Editor, changing scenes or closing the app

### Version 4.3.0
##### August 8, 2024
- [**Added**] HISPLAYER_EVENT_PLAYBACK_BUFFERING and EventPlaybackBuffering.
    - This event occurs whenever an internal playback is buffering
- [**Added**] New HISPlayer Video Uploader feature. Turn local videos into streaming videos such as HLS or DASH. This videos are going to be stored in our server for you. Please, on the Editor refer to:
    - [HISPlayer Video Upload documentation](https://hisplayer.github.io/UnityVideoUpload/#/)
- [**Improvement**] Optimized HISPlayer Settings log messages
- [**Improvement**] Optimized Event and Error listeners
- [**Improvement**] Optimized license checking
- [**Improvement**] Optimized HISPlayer API function commentaries to be more clear
- [**Improvement**] Optimized runtime log messages
- [**Improvement**] Optimized multistream performance

### Version 3.4.1
##### April 23, 2024
- [**Improvement**] Improvement of software robustness

### Version 3.4.0
##### April 10, 2024
- [**Added**] Multi stream support
- [**Added**] Local Playback Persistent Datapath support 
- [**Added**] HISPLAYER_ERROR_PLATFORM_NOT_REGISTERED error event
- [**Improvement**] Optimized HISPlayer Settings
    - A warning message will be displayed in case a field required by HISPlayer SDK is missing
- [**Improvement**] Optimized HISPlayer error event handler

### Version 3.3.0
##### January 25, 2024
- [**Added**] UWP support to multiplatform SDK
- [**Added**] New API to change video content using the URL string as a parameter:
    - **ChangeVideoContent(int playerIndex, string url)**
- [**Added**] HISPlayerError.HISPLAYER_ERROR_NETWORK_FAILED and ErrorNetworkFailed(HISPlayerErrorInfo errorInfo) event callback
    - It indicates if there is no Internet when starting the application
- [**Improvement**] Optimized error logs

### Version 3.2.0
##### December 7, 2023
- [**Added**] AutoTransition and LoopPlayback APIs
- [**Added**] Unity 2023 support

### Version 3.1.1
##### November 23, 2023
- [**Improvement**] Improvement of software robustness

### Version 3.1.0
##### October 11, 2023
- [**Improvement**] Improvement of software robustness

### Version 3.0.0 (Multiplatform SDK)
##### September 5, 2023
The Windows SDK is moved to multiplatform HISPlayerSDK (Android, iOS, macOS, WebGL, Windows)

Starting from version 3.0.0, the Windows SDK is part of multiplatform SDK

### Version 1.4.0
##### August 7, 2023
- [**Added**] Playback Speed Controller.
    - void SetPlaybackSpeedRate(int playerIndex, float speed);
    - float GetPlaybackSpeedRate(int playerIndex);   

### Version 1.3.0
##### June 23, 2023
- [**Added**] License key field.

### Version 1.2.0
##### June 19, 2023
- [**Improvement**] Optimized UWP playback.

### Version 1.1.0
##### April 20, 2023
- [**Added**] UWP support.

### Version 1.0.0
##### March 31, 2023
- [**Added**] Initial release of HISPlayer Windows SDK for Unity.
