# Setup Guide
Through this guide, you will be introduced to the basic steps for setting up the playback.

## Import Package
Importing the package is the same as importing other normal packages in Unity. Select the package of HISPlayer SDK and import it.

**Assets > Import Package > Custom Package**

## Configure Unity for Windows
Switch the platform for **Windows**. Open **File > Build Settings** and then select **Windows, Mac, Linux platform** for Windows Standalone build or select **Universal Windows Platform** for UWP build and **switch platform**.

Open **Player Settings > Other Settings**. Disable the **Auto Graphics API for Windows** option and make sure that only **‘Direct3D11’** macro is defined.

### <ins>UWP Settings</ins>
Open **Universal Windows Platform Settings > Player Settings > Publishing Settings > Capabilities**. Check the **InternetClient** option to enable internet access.

## Set up HISPlayerManager
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
