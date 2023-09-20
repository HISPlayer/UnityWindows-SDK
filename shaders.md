# Custom Shaders for Linear Color Space
Unity allows you to create [Custom Shaders](https://docs.unity3d.com/Manual/Shaders.html) to improve and generate your own materials 
and graphics. 

We provide examples that simulate the Gamma color space even if you are using Linear color space. The color space plays an important role when rendering the scene and there are differences between Gamma and Linear color spaces 
(refer to this [Unity Manual](https://docs.unity3d.com/Manual/LinearRendering-LinearOrGammaWorkflow.html))
 
If you follow the [Import Sample](https://hisplayer.github.io/UnityWindows-SDK/#/import-sample) section, please, refer to the GameObject **ScreenRawImage** and check the **Raw Image** component. You
will see there is a material attach to the **material** attribute named **HISPlayerDefaultMaterialRawImage**.

<p align="center">
<img width = "700" alt="image" src="https://github.com/HISPlayer/UnityWindows-SDK/assets/47497948/df0a69c4-0ee0-4812-ab9f-2c2c319ee6db">
</p>

This material is using the custom shader **HISPlayer/HISPlayerDefaultShaderRawImage**. 
For more details, you can check the following folders and files:

- **Packages/HISPlayer Windows SDK/HisPlayer/Scripts/Shaders/** - Here you can find the custom shaders. These files contain the code to simulate the Gamma color space when using Linear color space.
  - **HISPlayerDefaultShader.shader**
  - **HISPlayerDefaultShaderRawImage.shader**
 
<p align="center">
<img width = "600" alt="image" src="https://github.com/HISPlayer/UnityWindows-SDK/assets/47497948/fa79f193-7cd2-4709-a79a-6b0af5d987f3">
</p>

- **Packages/HISPlayer Windows SDK/HisPlayer/Resources/Materials/** - Here you can find 3 different Unity materials:
  - **HISPlayerDefaultMaterial.mat**: It uses the **HISPlayerDefaultShader.shader** and can be used for the HISPlayer RenderMode “Material”.
  - **HISPlayerDefaultMaterialRawImage.mat**: It uses the **HISPlayerDefaultShaderRawImage.shader** and can be used attaching the material to the material attribute of the RawImage component.
  - **HISPlayerDefaultMaterialRenderTexture.mat**: It uses the HISPlayerDefaultShader.shader and the HISPlayerDefaultRenderTexture.renderTexture.

<p align="center">
<img width = "600" alt="image" src="https://github.com/HISPlayer/UnityWindows-SDK/assets/47497948/77ef6736-000c-44c8-89b8-61fce0944007">
</p>

- **Packages/HISPlayer Windows SDK/HisPlayer/Resources/RenderTextures/**
  - **HISPlayerDefaultRenderTexture.renderTexture** - This file is a custom RenderTexture to be used with the **HISPlayerDefaultMaterialRenderTexture.mat**.
