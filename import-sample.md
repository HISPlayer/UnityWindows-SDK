# Import HISPlayer Sample

Please, download the sample here -> [**HISPlayer Sample**](https://downloads.hisplayer.com/Unity/AllPlatforms/HISPlayer_Sample.unitypackage) 
(no need to download it if you have received it in the email).

Importing the package is the same as importing other normal packages in Unity. Select the downloaded package and import it.

- **Assets > Import Package > Custom Package > HISPlayer_Sample.unitypackage**

<p align="center">
<img width=50% src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/95592ff6-8467-4137-9eda-d9cd3b387acb">
</p>

- Complete the configuration for Windows ->  [**Configure Unity for Windows**](./setup-guide.md#12-configure-unity-for-windows)

- Open the scene **Assets/HISPlayerSample/Scenes/HISPlayerSample.unity**

<p align="center">
  <img width=60% alt="image" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/0c4b5314-d835-4e56-879c-6d48c16312b2">
</p>

- Import TextMesh Pro Essential

- Input the license key through the Inspector. **HISPlayerController** GameObject -> **HISPlayerController** component -> **License Key**

<p align="center">
  <img width=80% alt="image" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/f99d01df-847e-4289-9a33-364ce9210e53">
</p>

- Open **File** > **Build Settings** > **Add Open Scenes**

<p align="center">
  <img width=70% alt="image" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/6c774c5f-2b81-4cd3-8588-b26f8ee92784">
</p>

- Build and Run

To check how to set up the SDK and API usage, please refer to **Assets/HISPlayerSample/Scripts/HISPlayerController.cs** and **HISPlayerController GameObject** in the Editor.

## MultiStream UI Demo
**Please, keep in mind multi stream is not supported for Windows yet. Only the left screen will display video.**

The UI components in the sample scene are fully modifiable and each stream has its own UI. The sample is intended to show a comprehensive scene using the HISPlayer SDK to help demonstrate features such as play, pause, seek, etc using the multi stream feature. 

<p align="center">
  <img width=55% alt="image" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/312e37e7-aff3-4537-8dc3-d5843b86441c">
</p>

<p align="center">
  <img width=90% alt="image" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/640453d1-8a58-45cf-9260-c659cb308655">
</p>

## Add/Remove URLs
In order to add/remove URLs, please refer to the component **HISPlayerController** attached to the **HISPlayerController GameObject** in the **Inspector**. 

### Change URL
To change the default video URL using your own URL, please replace the element value with your own URL in the **URL list** of the stream you want to modify.

<p align="center">
  <img width=60% alt="replace-url" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/5b876db4-f3c9-4c98-84df-f23737070f50">
</p>

### Add/Remove URLs

You can add/remove URLs by selecting one element from the **Multi Stream Properties list** and then pressing the buttons **+/-** in the **Url list**. For changing the content of the videos, please refer to **[ChangeVideoContent](https://hisplayer.github.io/UnityWindows-SDK/#/hisplayer-api?id=protected-void-changevideocontentint-playerindex-int-urlindex)** API.

<p align="center">
  <img width=70% alt="add-url" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/b65bf99f-202b-436e-a9c3-f1a6b9b97eaa">
</p>

