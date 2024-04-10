# Playing Local Files

HISPlayer Windows for Unity can play local content the [**Unity Streaming Assets**](./local-files.md#Unity-Streaming-Assets) and the [**Persistent Data Path**](./local-files.md#Persistent-Data-Path) (application's path) and absolute path. Streaming assets and persistent data path are supported from HISPlayer SDK v3.4.0. If you use SDK v3.3.0 and below, please refer to this section to play video using [**Absolute Path**](./local-files.md#Absolute-Path). 

## Unity Streaming Assets
To use this format, it’s necessary to create a new folder into the **Assets** folder of Unity named **StreamingAssets**.

<p align="center">
<img src="https://github.com/HISPlayer/UnityWindows-SDK/assets/32887298/d3f7f1d3-1dde-4bd8-bb10-a82a22e2f094">
</p>


### Video File
Add the video file inside the StreamingAssets folder and pass the file name (**with the extension**) to the **Multi Stream Properties**.
&nbsp;

<p align="center">
<img width = 70% src="./assets/content-strassets.png">
</p>

In case that subfolders are created inside StreamingAssets, the path of the file **must include the subfolder’s name** inside the field of Multi Stream Properties, e.g, with a subfolder named **“MyVideos”** the following path must be used: 

**MyVideos/localPlayback.mp4** 
&nbsp;

### HLS Manifest

Prepare a folder where all the HLS manifest files are stored, including the playlists and the segments. Pass the path of manifest file name with the extension (**.m3u8**) to the **Multi Stream Properties**. You may pass the master playlist or the media playlist. 

<p align="center">
  <img  width=50% src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/32887298/5769b2ca-f389-4a5e-9cd9-3ca790359147">
</p>

</br>

<p align="center">
  <img  width=50% src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/32887298/847de215-5e7f-4d9d-8486-04b93ec5470e">
</p>

If the content is encrypted with AES-128 key, the key file must be stored in the correct location following the `#EXT-X-KEY` tag URI in the manifest file. 

For example below *stream.m3u8* includes the following : `#EXT-X-KEY:METHOD=AES-128,URI="key.bin"`. The key file *key.bin* must exist in the valid path. 

<p align="center">
  <img  width=60% src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/32887298/c5c7b6c6-3dc7-463b-accf-61b732b08d22">
</p>

## Persistent Data Path
The [Persistent Data Path](https://docs.unity3d.com/ScriptReference/Application-persistentDataPath.html) is the internal path of the application.
Unity allows you to access that folder from the C-sharp code with **Application.persistentDataPath**.

The returned path on Windows will be: **%userprofile%/AppData/LocalLow/\<companyname>/\<productname>**.

The HISPlayer SDK will take this path as the entry point to begin to search the desired local content.

### Video File

Add the video file that is stored inside the application persistent data path and pass the file name (**with the extension**) to the **Multi Stream Properties**.
In case that subfolders are created inside *Application.persistentDataPath* , the path of the file **must include the subfolder’s name** inside the field
of Multi Stream Properties, e.g, with a subfolder named **“MyVideos”** the following path must be used: 

**MyVideos/localPlayback.mp4** 
&nbsp;

<p align="center">
  <img  width=50% src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/32887298/ee113d2d-6631-4cf7-86a8-ab20d79fcee1">
</p>

### HLS Manifest

Make sure all the HLS manifest files are stored in the *Application.persistentDataPath*, including the playlists and the segments. Pass the path of manifest file name with the extension (**.m3u8**) to the **Multi Stream Properties**. You may pass the master playlist or the media playlist. 

<p align="center">
  <img  width=50% src="https://github.com/HISPlayer/UnityWindows-SDK/assets/32887298/3b34db01-f6d4-47e0-883a-4795c98f7af4">
</p>

</br>

<p align="center">
  <img  width=50% src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/32887298/847de215-5e7f-4d9d-8486-04b93ec5470e">
</p>

If the content is encrypted with AES-128 key, the key file must be stored in the correct location following the `#EXT-X-KEY` tag URI in the manifest file. 

For example below *stream.m3u8* includes the following : `#EXT-X-KEY:METHOD=AES-128,URI="key.bin"`. The key file *key.bin* must exist in the valid path. 

<p align="center">
  <img  width=60% src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/32887298/227d6a63-128e-45f7-9275-7b2767a14087">
</p>

## Absolute Path
HISPlayer Windows SDK can play local content using the absolute path. For example : **C:/yourVideo.mp4** . 

Please input the absolute path where the video file is located to the Multi Stream Properties.

<p align="center">
<img src="https://github.com/HISPlayer/UnityWindows-SDK/assets/32887298/ca9bfff2-06fc-4cef-a92a-d7aaf2bbf1ee">
</p>

