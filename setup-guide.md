# QuickStart Guide
Getting started with HISPlayer consists of implementing the following steps:

1. Import and configure package   

      1.1. Import package
 
      1.2. Configure Unity for Windows
   
2. Create your own sample
   
    2.1 Setup HISPlayer Manager
   
    2.2 Attach Unity Resources
   
    2.3 Configure HISPlayer Properties

    2.4 Build and Run

It's also possible to import the [HISPlayer Sample](/import-sample.md) after completing step 1. The sample is a comprehensive example scene using the HISPlayerSDK to help demonstrate features like play, pause, seek, etc.

## 1.1 Import Package
Importing the package is the same as importing other normal packages in Unity. Select the package of HISPlayer SDK and import it.

**Assets > Import Package > Custom Package > HISPlayerWindowsSDK unity package**

<p align="center">
<img src="./assets/import-package.png">
</p>

## 1.2 Configure Unity for Windows
Switch the platform for **Windows**. Open **File > Build Settings** and then select **Windows, Mac, Linux platform** for Windows Standalone build or select **Universal Windows Platform** for UWP build and **switch platform**. 

Set **Architecture** to **Intel 64-bit**.

Open **Player Settings > Other Settings**. Disable the **Auto Graphics API for Windows** option and make sure that only **‘Direct3D11’** macro is defined.

### <ins>UWP Settings</ins>
Open **Universal Windows Platform Settings > Player Settings > Publishing Settings > Capabilities**. Check the **InternetClient** option to enable internet access.

## 2.1 Setup HISPlayer Manager
Create a script which is going to inherit from **HISPlayerManager**. It is needed to include the namespace by adding **‘using HISPlayerAPI;’** and add this component to a GameObject. It is recommended to create an **Empty GameObject** for this.

Call the **‘SetUpPlayer()’** function in order to initialize the stream environment internally. This function can be called whenever it’s needed.

For example, using the Awake function:
```C#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using HisPlayerAPI;

public class HISPlayerWindowsSample : HisPlayerManager
{
    protected override void Awake()
    {
        base.Awake();
        SetUpPlayer();
    }
}
```
It is strictly necessary to use **SetUpPlayer** before using anything else, because this function will initialize everything from the SDK in order to be able to use the rest of the functions (Play, Pause, Seek …).

## 2.2 Attach Unity Resources
Move to **Unity Editor** to attach all the resources. The rendering system is supporting **Material, RawImage, RenderTexture** and **NONE** (empty)  Unity’s components.

### <ins>Material</ins>
Create a new Material from **Assets > Create > Material** and attach it to the GameObject that is going to be used as screen and to the stream controller component. 

You can also use the **Resources > Materials > HISPlayerDefaultMaterial.mat** we provide in our package. 

<p align="center">
<img width=37% alt="image" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/eacab2a8-7cee-4218-add9-98672f250540">
<img width=45% alt="image" src="https://github.com/HISPlayer/UnityWebGL-SDK/assets/47497948/ffe0ea80-d66b-4fac-beb0-01152bce200e">
</p>

### <ins>Raw Image</ins>
This action will be related to Unity’s Canvas. If there is not a Canvas created yet, creating a **Raw Image** will create one automatically.

For the creation, select **GameObject > UI > Raw Image**. Once it is created, attach it to the stream controller component

<p align="center">
<img width="400" alt="image" src="https://github.com/HISPlayer/UnityWebGL-SDK/assets/47497948/5dcc7a3f-7de5-4e87-a5e3-3e08587360b4">
</p>

### <ins>RenderTexture</ins>
For this you can use the RenderTexture we provide or create a RenderTexture from zero. In the first case, go to the Resources folder of our package and attach the **Resources > Materials > HISPlayerDefaultMaterialRenderTexture.mat** to the GameObject that is going to be used as screen and the **Resources > RenderTextures > HISPlayerRenderTexture.renderTexture** to the stream controller component.

For creating it from zero, select **Assets > Create > Render Texutre** and then create a **Material** referencing the **Render Texture**. This last action can be done automatically by grabbing the **Render Texture** and dropping it at the end of a GameObject's Inspector with the component **Mesh Renderer** with **Material field empty**. This will create the new material inside a **Materials** folder. 

Once all this process it’s done, associate the **RenderTexture** to the script component.

<p align="center">
<img src="https://github.com/HISPlayer/UnityiOS-SDK/assets/47497948/a0f26bc1-c7b1-432e-ad87-1a2d203d32c8">
</p>

## 2.3 Configure HISPlayer Properties

### <ins>License Key</ins>
Input the license key that is associated with the SDK. If the license key is not valid, the player won't work and will throw an error message.

License key is not required for HoloLens SDK.

<p align="center">
<img width="400" src="./assets/license-key-windows.PNG">
</p>


### <ins>Multi Stream Properties</ins>

Use **Multi Stream Properties** to set all configurations needed for multi stream. However, currently HISPlayer Windows SDK only supports single stream. Multi stream support will be added in the future. It starts with 0 elements. Adding more elements will be ignored until multi stream support is supported. Each element added has its own configuration.

### <ins>Multi Stream Properties</ins>
Use Multi Stream Properties to set all the configuration needed for multi stream. However, currently HISPlayer Windows SDK only supports single stream. Multi stream support will be added in the future. It starts with 0 elements. Adding more elements will be ignored until multi stream support is supported. 

Each element added has its own configuration for multiple players and corresponds to 1 Render Surface. If you just need a single stream, then you just need to add 1 element with 1 URL.

* <span style="color:blue">**Render Mode**</span>: Select the render surface. It can be RenderTexture, Material, RawImage or NONE.
* <span style="color:blue">**Material**</span>: Attach the **Material** asset created to the **Material** section of the element.
* <span style="color:blue">**Raw Image**</span>: Attach the **RawImage** asset created to the **RawImage** section of the element.
* <span style="color:blue">**Render Texture**</span>: Attach the **RenderTexture** to the **RenderTexture** section of the element.
* <span style="color:blue">**URL**</span>: Add the URL associated to the stream. Each stream can have multiple URLs, therefore users can use the same render surface to play different URLs.
* <span style="color:blue">**Autoplay**</span>: Property to determine whether the player will start automatically after set up.
* <span style="color:blue">**LoopPlayback (Read-only)**</span>: Loop the current playback. It's true by default. To modify this value, please, use the Editor or the constructor **StreamProperties(loopPlayback, autoTransition)**.
* <span style="color:blue">**AutoTransition (Read-only)**</span>: Change the playback to the next video in the playlist. This action won't have effect when loopPlayback is true. It's false by default. To modify this value, please, use the Editor or the constructor **StreamProperties(loopPlayback, autoTransition)**.

<p align="center">
<img width="479" alt="image" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/7d94655c-2d91-4a1b-b90e-36ab1dbfa1da">
</p>

## 2.4 Build and Run
Once the configuration it’s done, open **‘Build Settings’** and press **‘Build And Run’**.
<p align="center">
<img src="./assets/build-run.png" width=60%>
</p>
