# Update the SDK

Through this guide, you will be introduced how to update the SDK if you already have installed the SDK previously. Please, restart the Editor before continuing.

## Remove Old Package

Remove the previous HISPlayer Windows SDK package from Unity Package Manager. 

**Window > Package Manager > Packages - HISPlayer > HISPlayer SDK > Remove**

<p align="center">
  <img width="793" alt="Remove" src="https://github.com/HISPlayer/UnityWebGL-SDK/assets/47497948/00071022-a78b-4b36-bd1d-eaf64aad49fc">
</p>

<br>

## Import New package

Importing the new package is the same as importing other normal packages in Unity. 
Select the package of HISPlayer SDK and import it.

**Assets > Import Package > Custom Package > HISPlayerSDK.unitypackage**

<p align="center">
<img width="450" src="./assets/import-package.png">
</p>

<br>

## Configure Unity for Windows
Open the window **Tools > HISPlayer** located in the upper side of the screen > Click on Player Settings Configuration > Select **Build Target to Standalone Windows x64** > Set all the required settings.

<p align="center">
<img width="319" alt="image" src="https://github.com/HISPlayer/UnityWindows-SDK/assets/47497948/0f8d483e-2e3a-4d97-8210-35b7741373c5">
</p>

### <ins>UWP Settings</ins>
Open **Universal Windows Platform Settings > Player Settings > Publishing Settings > Capabilities**. Check the **InternetClient** option to enable internet access.

## Update License Key
If you received a license key from HISPlayer, please input the license key in the License Key field.

<p align="center">
<img width=70% alt="image" src="https://github.com/HISPlayer/UnityWebGL-SDK/assets/47497948/50b10c75-c6e0-438d-ba1f-da6e66d51eed">
</p>

If the license key is not valid, the player won’t work and will throw an error message. License key is not required for Unity Editor usage.
