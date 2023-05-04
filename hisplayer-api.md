# HISPlayer API

## Public API
The following public APIs are provided by HISPlayerManager.

* **public List < StreamProperties > multiStreamProperties**: List of properties for multi stream. However, currently HISPlayer iOS SDK only supports single stream. Multi stream support will be added in the future. It starts with 0 elements. Adding more elements will be ignored until multi stream support is added.
* **public class StreamProperties**:
  * **public HISPlayerRenderMode renderMode**: Type of texture for rendering.
  * **public Material material**: Reference to the Unity Material.
  * **public RawImage rawImage**: Reference to the Unity Raw Image.
  * **public RenderTexture renderTexture**: Reference to the Unity Render Texture.
  * **public List<string> url**: List of the URLs for the stream.
  * **public bool autoPlay**: If true, the players will start playing automatically after set-up.
  * **public bool enableRendering**: Determines if the stream will be rendered or not. The value can change in every moment for toggling between render or non-render mode. If true, the player will be rendered. It can change in runtime.
  
* **public enum HISPlayerRenderMode**: Type of texture for rendering.
    * **RenderTexture**
    * **Material**
    * **RawImage**
    * **NONE**

* **public enum HISPlayerEvent**: The list of events provided by HISPlayer SDK. You can use the event using the virtual functions in the next section.
    * **HISPLAYER_EVENT_VIDEO_SIZE_CHANGE**
    * **HISPLAYER_EVENT_PLAYBACK_PLAY**
    * **HISPLAYER_EVENT_PLAYBACK_PAUSE**
    * **HISPLAYER_EVENT_PLAYBACK_STOP**
    * **HISPLAYER_EVENT_PLAYBACK_SEEK**
    * **HISPLAYER_EVENT_PLAYBACK_BUFFERING**
    * **HISPLAYER_EVENT_PLAYBACK_BUFFER_END**
    * **HISPLAYER_EVENT_VOLUME_CHANGE**
    * **HISPLAYER_EVENT_END_OF_CONTENT**
    * **HISPLAYER_EVENT_ON_STREAM_RELEASE**
    * **HISPLAYER_EVENT_TEXT_RENDER**
  
* **public struct HISPlayerEventInfo**: The information of the triggered event.
    * **public HISPlayerEvent eventType**: The type of the event triggered.
    * **public int playerIndex**: The index of the player where the event is triggered.
    * **public float param1**: This will have different meanings depending on the event (see more information in [Functions](#Functions)). If there is no information about the parameter, it will have the default value -1.
    * **public float param2**: This will have different meanings depending on the event (see more information in [Functions](#Functions)). If there is no information about the parameter, it will have the default value -1.
    * **public float param3**: This will have different meanings depending on the event (see more information in [Functions](#Functions)). If there is no information about the parameter, it will have the default value -1.
    * **public float param4**: This will have different meanings depending on the event (see more information in [Functions](#Functions)). If there is no information about the parameter, it will have the default value -1.
    * **public string stringInfo**: Log information about the event.

* **public struct HISPlayerCaptionElement**: The information of the triggered event turns into caption’s format.
    * **public int playerIndex**: The index of the player where the event is triggered.
    * **public string caption**: The next generated caption text.
  
* **public struct HISPlayerCaptionTrack**:
    * **public string id**: ID of the caption.
    * **public string language**: Language of the caption.
  
## Functions
The following functions are provided by **HISPlayerManager**. They are **not public** so it’s necessary to create a custom script which inherits from **HISPlayerManager**.

### Virtual functions
These functions can be overridden.
#### protected virtual void Awake()
MonoBehaviour function which will be called from the beginning of the scene. It can be overridden but to make the system work it’s necessary to call base.Awake() into the overridden function.

#### protected virtual void EventPlaybackReady(HISPlayerEventInfo eventInfo)
Override this method to add custom logic when **HISPlayerEvent.HISPlayer_EVENT_PLAYBACK_READY** is triggered.
This event occurs when the current playback of a stream is ready to be used.
Calling functions such as GetTracks before this event is triggered will provide null information.
 
#### protected virtual void EventVideoSizeChange(HisPlayerEventInfo eventInfo)
Override this method to add custom logic when **HisPlayerEvent.HISPLAYER_EVENT_VIDEO_SIZE_CHANGE** is triggered.
This event occurs whenever the internal video size of the current track changes.
This event is triggered by the ABR feature.
<table>
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>param1</td>
    <td>Width of the video.</td>
  </tr>
   <tr>
    <td>param2</td>
    <td>Heigth of the video.</td>
  </tr>
</table>

#### protected virtual void EventPlaybackPlay(HisPlayerEventInfo eventInfo)
Override this method to add custom logic when **HisPlayerEvent.HISPLAYER_EVENT_PLAYBACK_PLAY** is triggered.
This event occurs whenever an internal playback has been started.
 
#### protected virtual void EventPlaybackPause(HisPlayerEventInfo eventInfo)
Override this method to add custom logic when **HisPlayerEvent.HISPLAYER_EVENT_PLAYBACK_PAUSE** is triggered.
This event occurs whenever an internal playback has been paused.

#### protected virtual void EventPlaybackStop(HisPlayerEventInfo eventInfo)
Override this method to add custom logic when **HisPlayerEvent.HISPLAYER_EVENT_PLAYBACK_STOP** is triggered.
This event occurs whenever an internal playback has been stopped.

#### protected virtual void EventPlaybackSeek(HisPlayerEventInfo eventInfo)
Override this method to add custom logic when **HisPlayerEvent.HISPLAYER_EVENT_PLAYBACK_SEEK** is triggered.
This event occurs whenever an internal playback has been sought to a new time position.
 <table>
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>param1</td>
    <td>Value of the new track position in milliseconds.</td>
  </tr>
</table>

#### protected virtual void EventVolumeChange(HisPlayerEventInfo eventInfo)
Override this method to add custom logic when **HisPlayerEvent.HISPLAYER_EVENT_VOLUME_CHANGE** is triggered.
This event occurs whenever the volume has been modified.
 <table>
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>param1</td>
    <td>New value for the volume.</td>
  </tr>
</table>

#### protected virtual void EventEndOfContent(HISPlayerEventInfo eventInfo)
Override this method to add custom logic when **HISPlayerEvent.HISPLAYER_EVENT_END_OF_CONTENT** is triggered.
This event occurs whenever the player reaches the end of the playback.
 
#### protected virtual void EventOnStreamRelease(HISPlayerEventInfo eventInfo)
Override this method to add custom logic when **HISPlayerEvent.HISPLAYER_EVENT_ON_STREAM_RELEASE** is triggered.
This event occurs whenever a player/stream has been released
 
#### protected virtual void EventTextRender(HISPlayerCaptionElement subtitlesInfo)
Override this method to add custom logic when **HISPlayerEvent.HISPLAYER_EVENT_TEXT_RENDER** is triggered.
This event occurs whenever a caption's text has been generated.
  <table>
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>caption</td>
    <td>The next generated caption text.</td>
  </tr>
</table>

### Non-virtual functions 
These functions can’t be overridden and they can be used only inside the inherited script. If it’s needed to use some of these functions into the Unity scene, for example with buttons, it is needed to create a public function which connects the button with the API.

#### protected void SetUpPlayer()
Initialize the player video stream system internally. It is necessary to use this function before anything else.
 
#### protected void Release()
Free all resources internally.
 
#### protected void Play(int playerIndex)
Play a certain stream. The **playerIndex** is associated with the index of the element of **Multi Stream Properties**. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### protected void Pause(int playerIndex)
Pause a certain stream. The **playerIndex** is associated with the index of the element of **Multi Stream Properties**. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### protected void Stop(int playerIndex)
Stop a certain stream. The **playerIndex** is associated with the index of the element of **Multi Stream Properties**. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### protected void Seek(int playerIndex, long milliseconds)
Seek a certain stream to a certain time of the track in **milliseconds**. The stream is associated with the index of the element of **Multi Stream Properties**. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### protected void SetVolume(int playerIndex, float volume)
Modify the **volume** of a certain stream. The volume of the track value ranges between **0.0f** and **1.0f**. The **playerIndex** is associated with the index of the element of **Multi Stream Properties**. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### protected void ChangeVideoContent(int playerIndex, string url)
Change the video’s **url**  of a certain stream. This will close the current playback and open the **new url**. The **playerIndex** is associated with the index of the element of **Multi Stream Properties**. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### protected long GetVideoPosition(int playerIndex)
Provides information about the timeline position in milliseconds, of the current video of a certain stream. The playerIndex is associated with the index of the element of Multi Stream Properties. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### protected long GetVideoDuration(int playerIndex)
Provides information about the total duration in milliseconds, of the current video of a certain stream. The playerIndex is associated with the index of the element of Multi Stream Properties. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### public HISPlayerCaptionTrack[] GetCaptionTrackList(int playerIndex)
Provide information about all the captions of a certain stream. The **playerIndex** is associated with the index of the element of **Multi Stream Properties**. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### public int GetCaptionsCount(int playerIndex)
Obtain the number of captions of a  certain stream. The **playerIndex** is associated with the index of the element of **Multi Stream Properties**. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### public string GetCaptionID(int playerIndex, int ccTrackIndex)
Obtain the ID of a certain caption track of a certain stream. The **ccTrackIndex** is the caption track index to be selected. The **playerIndex** is associated with the index of the element of **Multi Stream Properties**. Currently multi stream is not supported and only **playerIndex 0** will be processed.
 
#### public string GetCaptionLanguage(int playerIndex, int ccTrackIndex)
Obtain the language of a certain caption track of a certain stream.  The **ccTrackIndex** is the caption track index to be selected. The **playerIndex** is associated with the index of the element of **Multi Stream Properties**. Currently multi stream is not supported and only **playerIndex 0** will be processed.
