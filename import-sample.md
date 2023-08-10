# Import HISPlayer Sample
Please, download the sample here -> [**HISPlayer Windows Sample**](https://downloads.hisplayer.com/Unity/Windows/HISPlayerWindowsSample.unitypackage) (no need to download it if you have received it in the email).

Importing the package is the same as importing other normal packages in Unity. Select the downloaded package and import it.

- **Assets > Import Package > Custom Package > HISPlayerWindowsSample.unitypackage**

<p align="center">
<img src="./assets/import-package.png">
</p>

- Complete the configuration for Windows ->  [**Configure Unity for Windows**](./setup-guide.md#12-configure-unity-for-windows)

- Open the scene **Assets/HISPlayerWindowsSample/Scenes/HISPlayerWindowsSample.unity**

<p align="center">
<img src="./assets/windowssample-openscene.PNG" width=50%>
</p>

- Import TextMesh Pro Essential

- Input the license key through the Inspector Window. **WindowsStreamController** game object -> **HISPlayerWindowsSample** component -> **License Key**

<p align="center">
<img src="./assets/license-key-windows.PNG">
</p>

- Open **File** > **Build Settings** > **Add Open Scenes**

<p align="center">
<img src="./assets/windowssample-buildsetting.PNG" width=80%>
</p>

- Build and Run

To check how to set up the SDK and API usage, please refer to **Assets/HISPlayerWindowsSample/Scripts/HISPlayerWindowsSample.cs** and **WindowsStreamController GameObject** in the Editor.

## UI Demo
The UI components in the sample scene are fully modifiable. The sample is intended to show a comprehensive scene using the HISPlayer SDK to help demonstrate features such as play, pause, seek, etc.

<p align="center">
<img src="./assets/windowssample-uicomponent.PNG">
</p>

<p align="center">
<img src="./assets/windowssample-uisample.PNG" width=80%>
</p>
